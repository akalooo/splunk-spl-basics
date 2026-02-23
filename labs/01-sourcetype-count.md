# Lab 01 — Count Events by Sourcetype (BOTS v3)

## Objective
Get an overview of which sourcetypes generate the most events in the BOTS v3 dataset.

## Dataset
- index: botsv3

## SPL Query
```spl
index=botsv3
| stats count as total_events by sourcetype
| sort - total_events
## Results Screenshot

![Lab 01 Results](lab01-results.png)

## Analysis

From the results we can see which sourcetypes generate the highest event volume in the environment.

This helps identify:
- Primary data sources available for investigation
- High-volume logs that may require tuning
- Potential areas for threat hunting focus
