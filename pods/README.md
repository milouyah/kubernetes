
# Create
```bash
$ kubectl run nginx-pod --image=nginx
# or
$ kubectl create deployment dpy-nginx --image nginx
```

# ReplicaSet (with Deployment)
```bash
$ kubectl scale deployment dpy-nginx --replicas=3
$ kubectl get pods -o wide
```

# Object Spec (yaml)
* see `echo-hname.yaml`

```
kubectl create -f ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
```

# apply
```
sed -i 's/replicas: 3/replicas:6/' ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
kubectl apply -f ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
```
* (-i : --in-place)

# cordon
```
kubectl cordon w3-k8s
```