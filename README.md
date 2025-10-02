# monitoring-k8s-with-victoriametrics-victorialogs

This repo holds code from my series of Medium articles on Kubernetes Monitoring — A Complete Solution.

The articles are here:

- Part 1, Architecture: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-1-architecture-eb5b998658d5
- Part 2, Instrumentation, Telemetry, Dashboarding, and Alerting: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-2-instrumentation-telemetry-dashboarding-and-91eb3c9abdbb
- Part 3, Metrics using the victoria-metrics-k8s-stack: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-3-metrics-using-the-victoria-metrics-k8s-stack-515d64b5f3ba
- Part 4, Automatically extracting etcd certificates into a secret in Talos with VictoriaMetrics: https://medium.com/itnext/automatically-extracting-etcd-certificates-into-a-secret-in-talos-with-prometheus-or-670047f66534
- Part 5, VictoriaMetrics Operator: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-5-victoriametrics-operator-4d27a13dac6a
- Part 6, Visualizing with Grafana: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-6-visualizing-with-grafana-956499ff4d87
- Part 7, Alerting: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-7-alerting-ab6bf26a722c
- Part 8, Logging with VictoriaLogs: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-8-logging-with-victorialogs-f17c44461034
- Part 9, Talos Linux System Logs with VictoriaLogs and Vector: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-9-talos-linux-system-logs-with-victorialogs-and-65c1f1e44a23
- Part 10, Kubernetes Event Logging to VictoriaLogs: https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-10-kubernetes-event-logging-to-victorialogs-2ddc086d7859

Still being written:

- Part 11, Tracing
- Part ???

# Repo Structure

The following directories are found in this repo:

- `helm-values`: Broken down into subdirectories by chart, you'll find `values.yaml` files in subdirectories here as referenced by the articles above.
- `images`: Images from the articles (may not be present at first).
- `manifests`: Broken down into subdirectories by chart/product, you'll find a variety of manifests here for various components discussed in the articles. These can be applied by `kubectl apply -f` as needed.
- `talos`: Any Talos linux [configuration](https://www.talos.dev/v1.11/talos-guides/configuration/) patches required from the articles.

# Note

In [Part 6](https://medium.com/itnext/kubernetes-monitoring-a-complete-solution-part-6-visualizing-with-grafana-956499ff4d87), I reference creating a secret. I have not provided a `secret.yaml` in the interest of practicing good security (aka, not commiting secrets to git). Instead, use the command from the article:

```shell
kubectl create secret generic -n victoria-metrics-k8s-stack grafana-admin-password --from-literal=admin-user=admin --from-literal=admin-password=someSecureP@ssWord
```

Make sure you use a better password!

# License

This repo is licensed under the GNU GENERAL PUBLIC LICENSE, Version 3 (aka GPLv3). See [LICENSE](LICENSE) document.
