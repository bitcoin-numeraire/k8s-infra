# Monitoring

This Helm chart deploys monitoring tools (Prometheus and Grafana) to a Kubernetes cluster, configured to monitor your Bitcoin node and other cluster services.

## Configuration

The `values.yaml` file contains configuration options for both Prometheus and Grafana. Key configurations include persistence settings for Grafana, datasource configurations, and Prometheus scrape configurations.

### Key Configuration Highlights

- `grafana`: Configuration for deploying Grafana, including persistence, plugins, and datasources setup.
- `prometheus`: Configuration for deploying Prometheus, including scrape configurations tailored for monitoring Kubernetes services and pods.

## Deployment

Ensure Helm is installed and your Kubernetes context is set correctly. To deploy the monitoring stack, navigate to the chart's directory and run:

```sh
helm install monitoring ./charts/monitoring -f charts/monitoring/values.yaml
```

This will deploy both Prometheus and Grafana with the configuration specified in `values.yaml`.

## Accessing Grafana and Prometheus

After deployment, access Grafana and Prometheus services via Kubernetes port forwarding or Ingress, if configured. Default Grafana credentials are specified in `values.yaml`; ensure to change these for production use.

## Customization

Modify `values.yaml` to adjust resource limits, enable additional Grafana plugins, or tweak Prometheus scrape configurations to fit your specific monitoring needs.

## Contributing

Contributions to improve the monitoring chart or add new features are welcome. Please adhere to the project's contribution guidelines when submitting changes.
