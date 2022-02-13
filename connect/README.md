
# [Accessing Clusters](https://kubernetes.io/docs/tasks/access-application-cluster/access-cluster/)

```bash
kubectl config view
```


# ETC
### [How to connect to a cluster with kubectl](https://www.scaleway.com/en/docs/compute/kubernetes/how-to/connect-cluster-kubectl/)


## Some useful kubectl commands
```bash
#show the full contents of your kubeconfig file
kubectl config view

#show the value of the current-context line of your kubeconfig file
kubectl config current-context

#show all of the Users currently defined in your kubeconfig file
kubectl config get-users

#show all of the Clusters currently defined in your kubeconfig file
kubectl config get-clusters

#show all of the Contexts currently defined in your kubeconfig file
kubectl config get-contexts
```