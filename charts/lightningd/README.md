# lightningd

This Helm chart deploys a Core Lightning (CLN) instance to a Kubernetes cluster, allowing you to participate in the Lightning Network for fast, scalable Bitcoin transactions.

## Configuration

The `values.yaml` file contains configuration options for the Lightning node, including network settings, image preferences, persistence for storing the Lightning Network data, and database connection configurations.

### Key Configuration

- `global.network`: Specify the Bitcoin network (`mainnet`, `testnet`, `regtest`) that the Lightning node will operate on.
- `image`: Docker image configuration for the Lightning node.
- `persistence`: Configuration for persistent storage to store the Lightning network data securely.
- `service`: Configuration for the Kubernetes service to expose the Lightning node's API and peer connections.
- `connectionstring`: Kubernetes Secret name containing the database connection string required for the Lightning node to store its state.
- `bitcoind`: Configuration parameters for connecting to a bitcoind node including service name and credentials.

## Deployment

To deploy the Lightning node, ensure Helm is installed and your Kubernetes context is set to the correct cluster. Run:

```sh
helm install lightningd ./charts/lightningd -f charts/lightningd/values.yaml
```

This command deploys the Lightning node to your Kubernetes cluster using the default configuration. Modify `values.yaml` to suit your specific requirements.

## Accessing the Lightning node

After deployment, access the Lightning node's API or connect to its peer network using the service created by the chart. Utilize port forwarding or an Ingress controller based on your cluster's setup.

## Monitoring

If monitoring tools are in place, configure them to include the Lightning node. Prometheus metrics can be exposed on a configurable port, typically set to monitor Lightning node activity and performance.

## Updating

To update your Lightning node deployment, adjust `values.yaml` as needed and then upgrade the release using Helm:

```sh
helm upgrade lightningd ./charts/lightningd -f charts/lightningd/values.yaml
```

## Security

Review and adjust the security settings provided by the chart according to your security standards, especially regarding the database connection and `bitcoind` access credentials.

## Support

For issues with the chart or feature requests, please reach out through GitHub by opening an issue or pull request.
