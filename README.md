# Helm Chart Repository

Welcome to the Vulboard Helm Chart Repository! This repository contains Helm charts for deploying and managing Vulboard applications on Kubernetes.

---

## Table of Contents

1. [Overview](#overview)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Development](#development)
5. [Contributing](#contributing)
6. [License](#license)

---

## Overview

This repository provides Helm charts to simplify the deployment of Vulboard on Kubernetes. Chart is located in its own directory within the repository, with a `Chart.yaml` file that describes the chart. The chart has dependencies on Postgres, kube-prometheus-stack and nats

### Features
- Easy deployment and management of Kubernetes.
- Configurable through `values.yaml`.
- Built-in support for common Kubernetes resources like deployments, services, and ingress.
- Built-in support for dependencies e.g Postgres,kube-prometheus-stack and nats.


---

## Installation

Before using the charts, ensure you have Helm installed. Follow the [official Helm installation guide](https://helm.sh/docs/intro/install/) if needed.

### Clone the Repository

```bash
git clone https://github.com/ankitdit06/vulboard-helm.git
cd vulboard-helm
```

### Install a Chart

To install a chart, use the following command:
```bash
helm install <release-name> . --namespace <namespace> --create-namespace
```

Replace the placeholders with appropriate values:
- `<release-name>`: A name for the Helm release.
- `<namespace>`: The Kubernetes namespace for the release.

---

## Usage

### Customizing Values

Customize the Helm chart by providing a `values.yaml` file or using the `--set` flag. For example:
```bash
helm install <release-name> . --values my-values.yaml
```
Or:
```bash
helm install <release-name> <repository-name>/<chart-name> --set key1=value1,key2=value2
```

### Upgrading a Release

To upgrade an existing release:
```bash
helm upgrade <release-name> . --values my-values.yaml
```

### Uninstalling a Release

To uninstall a release:
```bash
helm uninstall <release-name> --namespace <namespace>
```

---

## Development

### Directory Structure

Each Helm chart follows the standard directory structure:
```
<chart-name>/
├── Chart.yaml      # Chart metadata
├── values.yaml     # Default configurations
├── templates/      # Kubernetes manifest templates
└── README.md       # Chart-specific documentation
```

### Linting and Testing

Before submitting a new chart or changes, ensure that the chart passes linting and testing:
```bash
helm lint <chart-directory>
helm template <chart-directory>
```

---

## Contributing

We welcome contributions to this repository. To contribute:
1. Fork the repository and create a feature branch.
2. Make your changes and test them locally.
3. Submit a pull request with a detailed description of your changes.

Please ensure your contributions follow the [Helm best practices](https://helm.sh/docs/chart_best_practices/).

---

## License

This repository is licensed under the Apache License

---
