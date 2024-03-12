# bitcoind

This Helm chart deploys a Bitcoin node to a Kubernetes cluster.

## Configuration

The `values.yaml` file contains configuration options for the Bitcoin node. These include network settings, image preferences, and persistence options.

### Key Configuration

- `global.network`: Specify the Bitcoin network (`mainnet`, `testnet`, `regtest`).
- `image`: Docker image configuration for the Bitcoin node.
- `persistence`: Configuration for persistent storage to store blockchain data.
- `service`: Configuration for Kubernetes service to expose the Bitcoin node.

## Deployment

To deploy the Bitcoin node, first ensure you have Helm installed and your Kubernetes context is set to the correct cluster. Then run:

```sh
helm install bitcoind ./charts/bitcoind -f charts/bitcoind/values.yaml
```

This command deploys the Bitcoin node to your Kubernetes cluster using the default configuration. You can modify `values.yaml` to suit your specific requirements.

## Accessing the Bitcoin node

After deployment, you can access the Bitcoin node's RPC interface using the service created by the chart. Use port forwarding or an Ingress controller as appropriate for your environment.

## Monitoring

If you have monitoring tools deployed, ensure to configure them to monitor the Bitcoin node. This chart provides metrics on port 3000 by default.

## Updating

To update the Bitcoin node deployment, modify the values.yaml file as necessary and upgrade the release using Helm:

```sh
helm upgrade bitcoind ./charts/bitcoind -f charts/bitcoind/values.yaml
```

## Security

The chart configures the Bitcoin node with basic security settings. Ensure to review these settings and adapt them to your security requirements.

## Support

For issues with the chart or requests for new features, please submit an issue or pull request on GitHub.
