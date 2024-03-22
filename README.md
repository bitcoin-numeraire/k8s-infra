# Kubernetes Infrastructure Deployment

This repository contains Helm charts for deploying Numeraire Bitcoin services and related monitoring tools to a Kubernetes cluster.

## Structure

- `charts/`: Contains Helm charts for each component.
  - `bitcoind/`: Helm chart for deploying a Bitcoin node.
  - `monitoring/`: Helm chart for deploying monitoring tools.
  - `lightningd/`: Helm chart for deploying Core Lightning node + LSPD from Breez.
  - `networking/`: Helm chart for managing Ingress and cert-manager + any other dependencies that we may add in the future.

## Prerequisites

- Kubernetes cluster
- Helm 3

## Deployment

Each chart in the `charts/` directory contains its own README with specific deployment instructions. Follow these instructions to deploy each component to your Kubernetes cluster.

## Contributing

We welcome contributions to improve the charts and add new features. Please follow the standard Git flow process for submitting your changes.
