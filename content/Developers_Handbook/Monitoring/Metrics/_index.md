---
title: Metrics
weight: 2
---

## 101

[Prometheus](https://prometheus.io) is used to scrape `/metric` endpoints of
applications running in the cluster. _Metrics_ are numeric
measurements, which when scraped over time become _time series_ that describe
how the given application is running.

Metrics follow the following notation:

```text
<metric name>{<label name>=<label value>, ...}
```
A gauge is a metric that represents a single numerical value that can
arbitrarily go up and down. The following example _gauge metric_ indicates that
`http://data.norge.no/` returns the http status code `200`:

```text
probe_http_status_code{ingress="ingress-prod-v4", instance="http://data.norge.no/", namespace="prod"} 200
```

Another example is a _counter metric_, whose value may only increase or be reset
to zero:

```text
processed_mail_requests{fdk_service="fdk-mail-sender-service", status="success"} 7
```

One may based on metrics create rules that trigger alerts whenever an expression
is true. E.g. the expression `probe_http_status_code{} >= 500`, which indicates
than an application is unable to respond correctly.

See [Prometheus Introduction](https://prometheus.io/docs/introduction/overview/)
and [Metric Types](https://prometheus.io/docs/concepts/metric_types/) for a more
thorough introduction.

## Metric services
| Service | Purpose |
|---|---|
| [https://prometheus.fellesdatakatalog.digdir.no/rules](https://prometheus.fellesdatakatalog.digdir.no/rules) | Alert rules overview |
| [https://karma.fellesdatakatalog.digdir.no](https://karma.fellesdatakatalog.digdir.no) | Alerting dashboard |
| [https://thanos.fellesdatakatalog.digdir.no](https://thanos.fellesdatakatalog.digdir.no)  | Explore and query metrics |
| [https://alertmanager.fellesdatakatalog.digdir.no](http://alertmanager.fellesdatakatalog.digdir.no) | See alerts and silence them |
| [https://grafana.fellesdatakatalog.digdir.no](https://grafana.fellesdatakatalog.digdir.no) | Dashboards based on metrics | 


## Create metrics endpoint and expose metrics

See [Metric and label naming](https://prometheus.io/docs/practices/naming/) for best practices.

## Configure metrics scraping

Use the following pod annotations to configure scraping of metrics:

```yaml
annotations:
    # Enable scraping of metrics.
    prometheus.io/scrape: "true"
    # Specifies metrics port. Default: container's port.
    prometheus.io/port: "8080"
    # Specifies metrics path. Default: "/metrics".
    prometheus.io/path: "/metrics"
```

If you need more customization, such as scraping interval, look into using a
servicemonitor or podmonitor instead.


## Create alert rules
 
See [Alerting Rules](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules) for how to configure rules.  
Alerts fire in the `#fdk-dev-alerts` and `#fdk-prod-alerts` slack channels.  

`PrometheusRule` resources in the GitHub repo [fdk-infra/infrastructure/base/alerts](https://github.com/Informasjonsforvaltning/fdk-infra/tree/main/infrastructure/base/alerts) is used to configure alert rules, and will be automatically synced into Prometheus running in the clusters. Remember to add any new files within the _alerts_ folder to the `kustomization.yaml` `resources` list. 

```yaml
---
apiVersion: monitoring.coreos.com/v1
kind: PrometheusRule
metadata:
  name: <rule name - kebab case>
  namespace: monitoring
  labels:
    release: monitoring-kube-prometheus-stack
spec:
  groups:
    - name: fdk
      rules:
        - alert: <alert name - pascal case>
          annotations:
            description: <alert description (shown in slack)>
            summary: <alert title (shown in slack)>
          expr: <alert condition (e.g. "up{} == 0")>
          for: <time to wait before alerting (e.g. "0s")>
          labels:
            severity: <severity (none|info|warning|error|critical)>
            dashboard_url: <link to grafana/kibana dashboard, if any>
```
