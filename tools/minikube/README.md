
# [Minikube](https://minikube.sigs.k8s.io/docs/)

## [Install](https://minikube.sigs.k8s.io/docs/start/)
### Linux
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## Run
```bash
# Start
minikube start
# or
minikube start --force --driver=docker
kubectl get po -A
```

## Start
```bash
sudo minikube start --force --driver==docker
```

```bash
$ minikube ssh
```

## [Dashboard](https://minikube.sigs.k8s.io/docs/handbook/dashboard/)
```bash
minikube dashboard
```

# ETC
## How to access minikube machine from outside?
* see `https://stackoverflow.com/questions/54731887/how-to-access-minikube-machine-from-outside`
* [(모두의 MLOps) 4.2. Install Kubernetes - Minikube ](https://mlops-for-all.github.io/docs/setup-kubernetes/kubernetes-with-minikube/)