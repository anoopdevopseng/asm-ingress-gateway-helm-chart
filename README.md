# asm-ingress-gateway Helm Chart

This Helm chart deploys an Istio ingress gateway and related resources for Anthos Service Mesh on Kubernetes. It supports dynamic configuration for hosts, TLS secrets, backend configs, and more.

## Features
- Istio ingress gateway Deployment
- Configurable resource requests/limits
- Dynamic TLS and host configuration
- Optional static IP and security policy support
- BackendConfig for GCP health checks and security policies

## Usage

### 1. Install the chart
```sh
helm install <release-name> ./asm-ingress-gateway --values=values.yaml
```

### 2. Required values
Add these to your `values.yaml`:
```yaml
name: demo
namespace: istio-system
image: auto
hosts:
  - host: example.com
  - host: another.com
tlsSecretName: example-tls-secret
```

### 3. Optional values
```yaml
ingressStaticIP: my-static-ip
securityPolicy: my-cloud-armor-policy
resources:
  limits:
    cpu: 2000m
    memory: 1024Mi
  requests:
    cpu: 100m
    memory: 128Mi
```

## Validations
- The chart will fail if `tlsSecretName` or `hosts` is not provided.

## Example
See the provided `values.yaml` for a full example.