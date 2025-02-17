# Blobscan Helm Charts

[![Release Helm Charts](https://github.com/blobscan/blobscan-helm-charts/actions/workflows/release.yaml/badge.svg)](https://github.com/blobscan/blobscan-helm-charts/actions/workflows/release.yaml)

A set of [Helm](https://helm.sh/) charts to run blobscan on [Kubernetes](https://kubernetes.io/).

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add blobscan-helm-charts https://blobscan.github.io/blobscan-helm-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run the following command to see the charts.

```sh
helm search repo blobscan-helm-charts
```

To install the blobscan chart:

```sh
helm install blobscan blobscan-helm-charts/blobscan
```

To uninstall the chart:

```sh
helm delete blobscan
```

## List of charts

- [`blobscan`](charts/blobscan) - Blobscan is the first blockchain explorer that helps to navigate and visualize those EIP-4844 blobs.
- [`blobscan-api`](charts/blobscan-api) - Blobscan tRPC API.
- [`blobscan-indexer`](charts/blobscan-indexer) - Blobscan-Indexer indexes blobs in Postgresql for use with Blobscan.

## Development

### Prerequisites

- [`pre-commit`](https://pre-commit.com/) - Used to setup pre-commit git hooks
- [`docker`](https://www.docker.com/) - Used by many Makefile targets

### Pre-commit hooks

This repository used [`pre-commit`](https://pre-commit.com/) to manage and run certain git hooks. Hook definitions can be found within the [`.pre-commit-config.yaml`](.pre-commit-config.yaml) file.

Run the following to add the hooks to your local repository:

```sh
make init
```

### Useful commands

The `README` for every chart is auto generated using [helm-docs](https://github.com/norwoodj/helm-docs). This is defined as a pre-commit hook. If you want to run it manually, you can run:

```sh
make docs
```

The [CT (Chart Testing)](https://github.com/helm/chart-testing) tool is used to lint and validate charts. You can run this via:

```sh
make lint
```

## License

[MIT License](LICENSE)
