<img width="1583" height="753" alt="image" src="https://github.com/user-attachments/assets/c8582c78-e7be-47c2-b886-b53fe95aaa3b" /># Lab 03 — HTTP Anomaly Investigation (BOTS v3)

## Scenario
Investigate potential web scanning activity based on abnormal HTTP patterns.

## Dataset
- index: botsv3
- sourcetype: stream:http

## Investigation Steps
```spl
index=botsv3 sourcetype=stream:http status=404
| stats count as errors_404 by src_ip
| sort - errors_404
| head 10

index=botsv3 sourcetype=stream:http
| stats count as total_requests 
        sum(eval(status=404)) as errors_404 
        by src_ip
| eval error_ratio=round(errors_404/total_requests,2)
| sort - error_ratio
| head 10

## Results
(תמונות)

## Findings

## SOC Assessment

