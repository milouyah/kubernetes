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



## imagePullSecret
### [Pod](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/)
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: private-reg
spec:
  containers:
  - name: private-reg-container
    image: <your-private-image>
  imagePullSecrets:
  - name: regcred
```
### [ServiceAccounts](https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/)
```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  creationTimestamp: 2015-08-07T22:02:39Z
  name: default
  namespace: default
  uid: 052fb0f4-3d50-11e5-b066-42010af0d7b6
secrets:
- name: default-token-uudge
imagePullSecrets:
- name: myregistrykey
```