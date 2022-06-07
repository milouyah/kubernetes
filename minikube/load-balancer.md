# From 'Kubernetes in Action'


```
k apply -f kubia.yaml
k expose rc kubia --type=LoadBalancer --name kubia-http
```


# Troubleshooting
* [Minikube LB Pending](https://www.nakjunizm.com/2021/10/05/Minikube_ExternalIP_Pending/)
