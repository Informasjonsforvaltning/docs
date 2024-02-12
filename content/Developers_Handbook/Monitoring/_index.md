---
title: Monitoring
weight: 7
---

Monitoring is critical to a microservice architecture. In the following pages we
describe how we instrument our services in order to be properly monitored.

We use [Prometheus](https://prometheus.io/) and [Grafana](https://grafana.com/)
to monitor our services. They are configured and deployed from the
[fdk-infra](https://github.com/Informasjonsforvaltning/fdk-infra) repo. The
Grafana dashboards themselves are located in
[fdk-grafana-dashboards](https://github.com/Informasjonsforvaltning/fdk-grafana-dashboards).
