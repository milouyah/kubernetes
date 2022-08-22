# [Secret](https://kubernetes.io/docs/concepts/configuration/secret/)


## [Types of Secret](https://kubernetes.io/docs/concepts/configuration/secret/#secret-types)

```
Opaque	arbitrary user-defined data
kubernetes.io/service-account-token	ServiceAccount token
kubernetes.io/dockercfg	serialized ~/.dockercfg file
kubernetes.io/dockerconfigjson	serialized ~/.docker/config.json file
kubernetes.io/basic-auth	credentials for basic authentication
kubernetes.io/ssh-auth	credentials for SSH authentication
kubernetes.io/tls	data for a TLS client or server
bootstrap.kubernetes.io/token	bootstrap token data
```

### Opaque secrets

* `generic`

```bash
kubectl create secret generic empty-secret
kubectl get secret empty-secret
```


## [Create (Kubectl)](https://kubernetes.io/docs/tasks/configmap-secret/managing-secret-using-kubectl/)

* [docker-registry](https://medium.com/open-devops-academy/kubernetes-secrets-create-a-docker-registry-secret-a86cf3454981)