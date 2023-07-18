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

## Embed private dashboard

If you want to embed a dashboard but it has restricted access, you can use service account authentication.

This deployment have configuration to expose a pre-authorized endpoint, using service account token at subdomain (set by `${REDMIC_AUTH_TOKEN}`). Endpoint is generated with `${TRAEFIK_SUBDOMAIN}-${REDMIC_AUTH_TOKEN}.${PUBLIC_HOSTNAME}`.

Using this endpoint, only users who know this token will have access to a restricted dashboard when embedded into any subdomain of `${PUBLIC_HOSTNAME}`.
