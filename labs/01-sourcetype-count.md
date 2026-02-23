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

![Lab 01 Results](image.png)
