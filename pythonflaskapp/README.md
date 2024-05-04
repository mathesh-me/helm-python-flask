# Python Flask App Helm Chart

This Helm chart will deploy a Python Flask application to a Kubernetes cluster.

## Prerequisites

- `Kubernetes cluster`
- `Helm installed`

## Installation

1. Clone this repository:

```bash
git clone https://github.com/mathesh-me/helm-python-flask 
```

2. Install the chart:

```bash
helm install <release-name> ./helm-python-flask
```

Replace `<release_name>` with your desired release name.

## Parameters Configuration

The following table lists the configurable parameters and their default values:

| S.No. | Parameter                 | Description                                         | Default          |
|-------|---------------------------|-----------------------------------------------------|------------------|
|   1   | `deployment.replicas`     | Number of replicas                                  | `2`              |
|   2   | `deployment.image.owner`  | Image owner                                         | `memathesh`      |
|   3   | `deployment.image.repository` | Image repository                                | `pythonflaskapp` |
|   4   | `deployment.image.tag`    | Image tag                                           | `latest`         |
|   5   | `deployment.container.name` | Container name                                    | `pythonflaskapp` |
|   6   | `deployment.container.port` | Container port                                    | `80`             |
|   7   | `service.type`            | Kubernetes service type                             | `NodePort`       |
|   8   | `service.port`            | Service port                                        | `80`             |
|   9   | `service.targetPort`      | Target port                                         | `80`             |
|  10   | `service.nodePort`        | Node port (for `NodePort` service type)             | `30007`          |

To override these default values, you can specify the parameters using the `--set` flag during installation. For example:
```bash
helm install <release_name> ./helm-python-flask --set deployment.replicas=3
```


## Usage

Once the chart is installed, you can access the deployed Python Flask application by accessing the service using the specified service port or NodePort.
```
http://<node-ip>:<node-port>
```

Replace `<node-ip>` with the IP address of the Kubernetes node and `<node-port>` with the NodePort value specified during installation.

## Uninstallation

To uninstall the chart, use the following command:

```bash
helm uninstall <release-name>
```
Replace `<release-name>` with the release name used during installation.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

- [Mathesh M](https://www.linkedin.com/in/mathesh-me/) on LinkedIn.
- **Email:** itzmathesh@gmail.com

**Contributions are always welcome! You can contribute to this Chart by creating a Pull Request.**
