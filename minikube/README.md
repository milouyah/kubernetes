
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



## Start
### Linux
```bash
sudo minikube start --force --driver==docker
```

```bash
$ minikube ssh
```

### Run
```bash
$ kubectl cluster-info
$ kubectl get nodes
$ kubectl get pods -A
```


### [services](./services.md)
### [nodes](./nodes.md)
### [pods](./pods.md)