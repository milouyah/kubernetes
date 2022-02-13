# [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)
The kubectl command line tool lets you control Kubernetes clusters. For configuration, kubectl looks for a file named `config` in the `$HOME/.kube` directory. You can specify other kubeconfig files by setting the `KUBECONFIG` environment variable or by setting the `--kubeconfig` flag.

## [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
## [kubectl-commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)


* [List All Container Images Running in a Cluster](https://kubernetes.io/docs/tasks/access-application-cluster/list-all-running-container-images/)

```bash
$ kubectl get pods --all-namespaces
```