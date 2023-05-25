# Flux monitoring

[docs](https://fluxcd.io/docs/guides/monitoring/)

## Update fluxcd dashboards

```sh
wget -O podmonitor.yaml "https://raw.githubusercontent.com/fluxcd/flux2/main/manifests/monitoring/monitoring-config/podmonitor.yaml"
wget -O cluster.json "https://raw.githubusercontent.com/fluxcd/flux2/main/manifests/monitoring/monitoring-config/dashboards/cluster.json"
wget -O control-plane.json "https://raw.githubusercontent.com/fluxcd/flux2/main/manifests/monitoring/monitoring-config/dashboards/control-plane.json"
wget -O logs.json "https://raw.githubusercontent.com/fluxcd/flux2/main/manifests/monitoring/monitoring-config/dashboards/logs.json"
```
