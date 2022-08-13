# [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)
The kubectl command line tool lets you control Kubernetes clusters. For configuration, kubectl looks for a file named `config` in the `$HOME/.kube` directory. You can specify other kubeconfig files by setting the `KUBECONFIG` environment variable or by setting the `--kubeconfig` flag.

## [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
## [kubectl-commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)


* [List All Container Images Running in a Cluster](https://kubernetes.io/docs/tasks/access-application-cluster/list-all-running-container-images/)

```bash
$ kubectl get pods --all-namespaces
$ kubectl get pods -o wide
```


# Commnads
## [Mater node](https://stackoverflow.com/questions/63549272/how-to-list-only-nodes-which-are-master-from-kubectl-output)
```
kubectl get nodes -l node-role.kubernetes.io/master -o 'jsonpath={.items[*].metadata.name}'
```

## Logs
```
kubectl logs my-pod                                 # dump pod logs (stdout)
kubectl logs -l name=myLabel                        # dump pod logs, with label name=myLabel (stdout)
kubectl logs my-pod --previous                      # dump pod logs (stdout) for a previous instantiation of a container
kubectl logs my-pod -c my-container                 # dump pod container logs (stdout, multi-container case)
kubectl logs -l name=myLabel -c my-container        # dump pod logs, with label name=myLabel (stdout)
kubectl logs my-pod -c my-container --previous      # dump pod container logs (stdout, multi-container case) for a previous instantiation of a container
kubectl logs -f my-pod                              # stream pod logs (stdout)
kubectl logs -f my-pod -c my-container              # stream pod container logs (stdout, multi-container case)
kubectl logs -f -l name=myLabel --all-containers    # stream all pods logs with label name=myLabel (stdout)
```


# ETC

##[ `kubectl create` vs `kubectl apply`](https://may9noy.tistory.com/302#:~:text=%EC%89%BD%EA%B2%8C%20%EB%A7%90%ED%95%B4%2C%20create%20%EB%AA%85%EB%A0%B9%EC%96%B4%EB%8A%94,%EC%9E%98%20%EC%A7%84%ED%96%89%20%EB%90%9C%EB%8B%A4%EB%8A%94%20%EB%9C%BB%EC%9E%85%EB%8B%88%EB%8B%A4.)