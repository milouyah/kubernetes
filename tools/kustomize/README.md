# [kustomize](https://kustomize.io/)



# From Book
## 작동 원리
* kustomize create --> kustomization.yaml --> deploy-metalib.yaml

### Install Kustomize
```bash
~/_Book_k8sInfra/ch5/5.2.2/kustomize-install.sh
kustomize create --namespace=metallb-system --resources namespace.yaml,metallb.yaml,metallb-l2config.yaml
kustomize edit set image metallb/controller:v0.8.2
kustomize edit set image metallb/speaker:v0.8.2

kustomize build | kubectl apply -f - 
kubectl get pods -n metallb-system
kubectl get configmap -n metallb-system
kubectl describe pods -n metallb-system | grep Image:

kubectl create deployment echo-ip --image=sysnet4admin/echo-ip
kubectl expose deployment echo-ip --type=LoadBalancer --port=80
kubectl get service echo-ip

# delete
kustomize build | kubectl delete -f -
kubectl delete service echo-ip
kubectl delete deployment echo-ip

```
