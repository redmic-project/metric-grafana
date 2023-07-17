# Grafana

Metrics visualization

## Provide dashboards

You can provide dashboard definitions at startup, mounted at `${DASHBOARDS_PATH}/` using configs or binding a volume.

## Update dashboards manually

When updating a dashboard via JSON Model (copy & paste), you have to pay attention to:

* Make sure `id` field has same value as previous version.
* Make sure `uid` field has same value as previous version.
* Set `version` field to current version number of the dashboard you are updating (Grafana will add +1 automatically).

These values will be different tipically when updating from `dev` to `pro` environment, for example.
