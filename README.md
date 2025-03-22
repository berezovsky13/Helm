# Simple Helm Chart

This is a basic Helm chart that deploys both nginx and Apache web servers.

## Installation

To install the chart:

```bash
helm install my-release .
```

## Configuration

The following table lists the configurable parameters and their default values:

| Parameter | Description | Default |
|-----------|-------------|---------|
| `nginx.replicaCount` | Number of nginx replicas | `1` |
| `nginx.image.repository` | Nginx container image repository | `nginx` |
| `nginx.image.tag` | Nginx container image tag | `latest` |
| `nginx.image.pullPolicy` | Nginx container image pull policy | `IfNotPresent` |
| `nginx.service.type` | Nginx Kubernetes service type | `ClusterIP` |
| `nginx.service.port` | Nginx Kubernetes service port | `80` |
| `nginx.container.port` | Nginx container port | `80` |
| `apache.replicaCount` | Number of Apache replicas | `1` |
| `apache.image.repository` | Apache container image repository | `httpd` |
| `apache.image.tag` | Apache container image tag | `latest` |
| `apache.image.pullPolicy` | Apache container image pull policy | `IfNotPresent` |
| `apache.service.type` | Apache Kubernetes service type | `ClusterIP` |
| `apache.service.port` | Apache Kubernetes service port | `80` |
| `apache.container.port` | Apache container port | `80` |

## Usage

To override default values, create a `custom-values.yaml` file and specify your values:

```bash
helm install my-release . -f custom-values.yaml
```

For example, to modify the number of replicas for nginx:

```yaml
nginx:
  replicaCount: 3
```

Or to modify Apache's image tag:

```yaml
apache:
  image:
    tag: "2.4"
``` 