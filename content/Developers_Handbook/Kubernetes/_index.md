---
title: Kubernetes
weight: 11
---

Kubectl alias (replace `<project>`, `<project>`, `<region>`, and `<namespace>`):

```bash
alias kprod='gcloud config set project <project>; gcloud container clusters get-credentials <project> --region <region>; kubectl config set-context --current --namespace=<namespace>'
```

Delete all Trivy vulnerability reports:

```bash
kubectl get vulnerabilityreports.aquasecurity.github.io | awk '{print $1}' | xargs kubectl delete vulnerabilityreports.aquasecurity.github.io
```

Search for specific vulnerability (replace `<vuln-to-search-for>`):

```bash
kubectl get vulnerabilityreports.aquasecurity.github.io -o json | jq -c .items[].report.vulnerabilities[] | grep <vuln-to-search-for> | jq -rc "[.resource,.installedVersion,.title]" | sort | uniq
```

Set node label (replace `<nodename>` and `<label>` (eg `app=static-rdf`)):

```bash
kubectl get nodes --show-labels
kubectl label nodes <nodename> <label>
```
