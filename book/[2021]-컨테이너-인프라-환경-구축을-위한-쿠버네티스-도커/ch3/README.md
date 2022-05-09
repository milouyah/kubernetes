# 3장, 컨테이너를 다루는 표준 아키텍처, 쿠버네티스


쿠버네티스 구성 방법  
1. Public cloud : EKS AKS, GKE
2. 설치형 쿠버네티스(유료) - Rnacher, OpenShift(RedHat)
3. 쿠버네티스 클러스터 자동 구성 - [`kubeadm`](https://kubernetes.io/docs/reference/setup-tools/kubeadm/), kops(Kubernetes Operations), KRIB, kubespray


---
## 3.1 쿠버네티스 이해하기
- 3.1.3 쿠버네티스 구성하기
- 3.1.6 쿠버네티스 구성 요소의 기능 검증하기


## `3.2 쿠버네티스 기본 사용법 배우기`
### 3.2.1 파드를 생성하는 방법

```bash
$ kubectl run nginx-pod --image=nginx

$ kubectl create deployment dpy-nginx --image nginx
```

* `run` vs `create deployment`
> - run : 단일 Pod 1개 만 생성하고 관리
> - create deployment - Deployment 라는 관리 그룹 내에서 파드가 생성


### 3.2.2 Object란?
* pod/deployment --> `spec` and `status` 등의 값을 가지고 있슴

* 기본 object
```
Pod
Namespaces
Volumne
Service
```
* Deployment
* DeamonSet
* ConfigMap
* ReplicaSet
* PV(Persistent Volumen)
* PVC(Persistent Volume Chain)
* StatefulSet

### 3.2.3 레플리카셋으로 파드 수 관리하기

* ReplicaSet (with Deployment)
```bash
$ kubectl scale deployment dpy-nginx --replicas=3
$ kubectl get pods -o wide
```

### 3.2.4 스펙 지정해 오브젝트 생성하기
```
kubectl create -f ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
sed -i 's/replicas: 3/replicas:6/' ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
```
* (-i : --in-place)

### 3.2.5 apply로 오브젝트 생성하고 관리하기
```
 kubectl apply -f ~/_Book_k8sInfra/ch3/3.2.4/echo-hname.yaml
```

### 3.2.8 노드 자원 보호하기
### 3.2.10 파드 업데이트하고 복구하기

## 3.3 쿠버네티스 연결을 담당하는 서비스

`Service` : K8S에 접속하는 방법

- 3.3.1 가장 간단하게 연결하는 노드포트

```bash
$ kubectl create deployment np-pods --image=sysnet4admin/echo-hname
$ kubectl create -f ~/_Book_k8sInfra/ch3/3.3.1/nodeport.yaml$
```

* expose
```bash
kbuectl expose deployment np-pods --type=NodePort --name=np-svc-v2 --port:80
```


- 3.3.2 사용 목적별로 연결하는 인그레스
- 3.3.4 온프레미스에서 로드밸런서를 제공하는 MetalLB
- 3.3.5 부하에 따라 자동으로 파드 수를 조절하는 HPA(Horizontal Pod Autoscaler)



## 3.4 알아두면 쓸모 있는 쿠버네티스 오브젝트
- 3.4.1 데몬셋
- 3.4.2 컨피그맵
- 3.4.3 PV와PVC
- 3.4.4 스테이트풀셋
  

* 네트워크 플러그인 : `CNI(Container Netowrk Interface)` - `Calico`, Flannel, Cilium, Kube-rotuer, Romana, WeaveNet, Cannal