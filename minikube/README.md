
# [Minikube](https://minikube.sigs.k8s.io/docs/)


## Installation
### Linux

```bash
# Install
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start
minikube start
kubectl get po -A
```

* Minikube: https://kubernetes.io/docs/tasks/tools/install-minikube/

```bash
$ minikube ssh
```

```bash
$ kubectl cluster-info
Kubernetes control plane is running at https://127.0.0.1:53673
CoreDNS is running at https://127.0.0.1:53673/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
```

```bash
kubectl get nodes
NAME       STATUS   ROLES                  AGE    VERSION
minikube   Ready    control-plane,master   112m   v1.23.1
PS C:\WINDOWS\system32>
```