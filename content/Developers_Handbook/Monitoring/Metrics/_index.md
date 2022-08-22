---
title: Metrics
weight: 2
---

Use the following pod annotations to configure scraping of metrics:

```yaml
annotations:
    # Enable scraping of metrics.
    prometheus.io/scrape: 'true'
    # Specifies metrics port. Default: container's port.
    prometheus.io/port: '8080'
    # Specifies metrics path. Default: '/metrics'.
    prometheus.io/path: '/metrics'
```

If you need more customization, such as scraping interval, look into using a
servicemonitor or podmonitor instead.
