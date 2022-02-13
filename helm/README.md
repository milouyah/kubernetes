# [helm](https://helm.sh/)
* https://github.com/helm/helm

## Install Helm
```bash
choco install kubernetes-helm
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