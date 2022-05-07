
# [Minikube](https://minikube.sigs.k8s.io/docs/)


## Installation
### Linux

```bash
# Install
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start
minikube start
# or
minikube start --force --driver=docker
kubectl get po -A
```


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


# ETC
## How to access minikube machine from outside?
* see `https://stackoverflow.com/questions/54731887/how-to-access-minikube-machine-from-outside`