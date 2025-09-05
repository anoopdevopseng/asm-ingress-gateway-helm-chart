# 🚀 asm-ingress-gateway Helm Chart

This Helm chart deploys an ASM ingress gateway and related resources for Anthos Service Mesh on GKE. It supports dynamic configuration for hosts, TLS secrets, backend configs, and more.

---

## ✨ Features
- ASM ingress gateway Deployment
- Configurable resource requests/limits
- Dynamic TLS and host configuration
- Optional static IP and security policy support
- BackendConfig for GCP health checks and security policies

---

## 📦 Usage

---

## 🌐 Using the Chart from GitHub Pages

Once published, you can add and use this Helm chart directly from GitHub Pages:

### 🛠️ Add the Helm Chart Repository & Install
```sh
helm repo add gateways https://anoopdevopseng.github.io/asm-ingress-gateway-helm-chart
helm repo update
helm install <release-name> gateways/asm-ingress-gateway --values=values.yaml
```

- `<release-name>`: Your desired release name
- `values.yaml`: Ensure it contains all required values
- Replace `<release-name>` with your desired release name.
- Make sure your `values.yaml` contains the required values (see above).

💡 **Tip:** Run `helm repo update` to get the latest chart version!

---

### 1️⃣ Install the chart
```sh
helm install demo ./asm-ingress-gateway --values=values.yaml
```

### 2️⃣ Required values
Add these to your `values.yaml`:
```yaml
name: demo
namespace: istio-system
hosts:
  - host: example.com
  - host: another.com
tlsSecretName: example-tls-secret
```

### 3️⃣ Optional values
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

---

## ✅ Validations
- The chart will fail if `tlsSecretName` or `hosts` is not provided.

---

## Example
See the provided `values.yaml` for a full example.