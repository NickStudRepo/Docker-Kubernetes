# Exercise Portainer

During this exercise, you will deploy Portainer on Kubernetes using either Kubernetes YAML manifests or Helm. You have the option to expose Portainer using NodePort or LoadBalancer. Note: Do not deploy both the LoadBalancer and NodePort versions simultaneously.

Portainer can be used to manage your Kubernetes cluster.

## Prerequisites

- Kubernetes cluster (can be activated in Docker Desktop)
- [kubectl](https://kubernetes.io/docs/tasks/tools/) (included in Docker Desktop)
- [helm](https://helm.sh/docs/intro/install/) (optional)

---

## Deploy Portainer using Kubernetes YAML manifests

Choose either NodePort or LoadBalancer for exposure, but do not deploy both at the same time.

### Deploy and expose via NodePort

```bash
kubectl apply -n portainer -f https://downloads.portainer.io/ce2-19/portainer.yaml
```

### Deploy and expose via LoadBalancer

```bash
kubectl apply -n portainer -f https://downloads.portainer.io/ce2-19/portainer-lb.yaml
```

### Get the deployment status

```bash
kubectl rollout status deployment/portainer -n portainer
kubectl get pod -n portainer -o wide
```

### Cleanup

```bash
kubectl delete -n portainer -f https://downloads.portainer.io/ce2-19/portainer.yaml
# or for LoadBalancer
kubectl delete -n portainer -f https://downloads.portainer.io/ce2-19/portainer-lb.yaml
```

---

## Deploy Portainer using Helm

### Add the Portainer Helm repository

```bash
helm repo add portainer https://portainer.github.io/k8s/
helm repo update
```

### Install Portainer

Choose either NodePort or LoadBalancer for exposure, but do not deploy both at the same time.

#### Expose via NodePort (default)

```bash
helm upgrade --install --create-namespace -n portainer portainer portainer/portainer
```

#### Expose via LoadBalancer

```bash
helm upgrade --install --create-namespace -n portainer portainer portainer/portainer --set service.type=LoadBalancer
```

### Access Portainer

- When using NodePort on Docker Desktop, access Portainer at:
  - http://localhost:30777
  - https://localhost:30779

- When using LoadBalancer on Docker Desktop, access Portainer at:
  - http://localhost:9000
  - https://localhost:9443

### Cleanup

```bash
helm uninstall -n portainer portainer
```