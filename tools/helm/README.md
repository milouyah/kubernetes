# [helm](https://helm.sh/)
* [github](https://github.com/helm/helm)
* K8S Package Manager
```
- Package 검색
- Package 관리
- Package dependency 관리
- Package security 관리
```

## Install Helm

### Windows
```bash
choco install kubernetes-helm
```
### Linux
```bash
```

## Initialize a Helm Chart Repository
```
$ helm repo add bitnami https://charts.bitnami.com/bitnami
```

## Install an Example Chart
```
helm repo update 
helm install bitnami/mysql --generate-name 
```

# From Book
```
export DESIRED_VERSION=v3.2.1;~/_Book_k8sInfra/ch5/5.2.3/helm-install.sh
helm repo add edu https://iac-source.github.io/helm-charts
helm repo list
helm repo update

helm install metallb edu/metallb \
--namespace=metallb-system \
--create-namespace \
--set controller.tag=v0.8.3 \
--set speaker.tag=v0.8.3 \
--set configmap.ipRange=192.168.1.11-192.168.1.29

```

* https://artifacthub.io/ --> metallb(helm)


## Books
## Learning

