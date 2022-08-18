
# [Pods](https://kubernetes.io/docs/concepts/workloads/pods/)

## [Volumes](./Volumes/README.md)
## [Label](./Label/README.md)



## 2. Annotaion
```
kubectl annotate pod kubia-manual mycompany.com/someannotation="foo.bar"
```

## 3. Namespace
* Kubernetes namesapce : 오브젝트 이름의 범위를 제공한다.

### get ns
```bash
kubectl get ns
kubectl get po --namesapce kube-system # or -n
```

### create ns
```
apiVersion: v1
kind: Namespace
metadata:
  name: custom-namespace
```

```
kubectl create namespace custom-namespace
```

```
kubectl create -f kubia-manual.yaml -n custom-namespace
```


## 4. Get
```bash
kubectl get po [pod-name] -o yaml
```


## Create
```bash
$ kubectl run nginx-pod --image=nginx
# or
$ kubectl create deployment dpy-nginx --image nginx
```

```
kubectl apply -f https://k8s.io/examples/pods/simple-pod.yaml
```

## ReplicaSet (with Deployment)
```bash
$ kubectl scale deployment dpy-nginx --replicas=3
$ kubectl get pods -o wide
```

## Object Spec (yaml)
* see `echo-hname.yaml`

```
kubectl create -f ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
```

## apply
```
sed -i 's/replicas: 3/replicas:6/' ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
kubectl apply -f ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
```
* (-i : --in-place)

## cordon
```
kubectl cordon w3-k8s
```

## Port forwarding
```
kubectl port-forwarding kubia-manual 8888:8080
```