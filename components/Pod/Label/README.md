## [Label](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/)

* Key:Value
```
kubectl get po --show-labels
kubectl get po -L creation_method,env
kubectl label po kubia-manual creation_method=manual # pod 'kubia-manual' labeled
kubectl label po kubia-manual-v2 env=debug --overwrite
``` 

```bash
kubectl get po -l creation_method=manual
kubectl get po -l env
kubectl get po -l '!env'
```

```
creation_method!=manual
env in (prod,devel)
env notin (prod,eval)
```

* nodeSelector
```
...
spec:
  nodeSelector:
    gpu: "true"
  containers:
  - image: luksa/kubia
    name: kubia
```