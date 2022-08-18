## Getting ready
* VirtualBox: https://www.virtualbox.org/wiki/Downloads
* Kubectl: https://kubernetes.io/docs/tasks/tools/install-kubectl/

> * windows
```bash
choco install kubernetes-cli
kubectl version --client
cd ~ # cd %USERPROFILE%
mkdir .kube
cd .kube
New-Item config -type file
``` 


* Minikube: https://kubernetes.io/docs/tasks/tools/install-minikube/

```bash
$ minikube start
$ minikube ssh
```

```bash
$ kubectl cluster-info
Kubernetes control plane is running at https://127.0.0.1:53673
CoreDNS is running at https://127.0.0.1:53673/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
```

```bash
kubectl get nodes
NAME       STATUS   ROLES                  AGE    VERSION
minikube   Ready    control-plane,master   112m   v1.23.1
PS C:\WINDOWS\system32>
```