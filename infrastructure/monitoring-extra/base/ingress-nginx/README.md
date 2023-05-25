# Nginx dashboards

```sh
wget -O nginx-controller.json https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/grafana/dashboards/nginx.json
wget -O request-handling-performance.json https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/grafana/dashboards/request-handling-performance.json
```

## Nginx analytics dashboard

Based on https://grafana.com/grafana/dashboards/12559 but heavily modified



Service Monitor is from official helm chart

Prometheus rule is based on official helm chart comments
