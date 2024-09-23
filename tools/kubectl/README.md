# [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)

The kubectl command line tool lets you control Kubernetes clusters. 

For configuration, kubectl looks for a file named `config` in the `$HOME/.kube` directory. 

You can specify other kubeconfig files by setting the `KUBECONFIG` environment variable or by setting the `--kubeconfig` flag.


## Install `kubectl`
네, **`kubectl`**은 Kubernetes 클러스터를 관리하는 커맨드 라인 도구로, 별도로 설치해야 합니다. `kubectl`은 Kubernetes API와 통신하여 클러스터 관리 작업을 수행합니다. Ubuntu에서 `kubectl`을 설치하려면 다음 단계를 따르면 됩니다.

### Ubuntu

#### 1. Google Cloud의 APT 저장소 추가

먼저, `kubectl` 패키지를 받기 위해 Google Cloud의 APT 저장소를 추가해야 합니다.

```bash
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl
curl -fsSL https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
```

#### 2. Kubernetes APT 저장소 추가

Google Kubernetes APT 저장소를 추가합니다.

```bash
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
```

#### 3. `kubectl` 설치

저장소를 추가한 후, `kubectl`을 설치합니다.

```bash
sudo apt-get update
sudo apt-get install -y kubectl
```

#### 4. 설치 확인

설치가 완료되면 `kubectl`이 제대로 설치되었는지 확인할 수 있습니다.

```bash
kubectl version --client
```

이 명령어를 실행하면, 설치된 `kubectl` 버전 정보가 출력됩니다.

### 5. `kubectl` 사용

`kubectl`이 설치된 후, 클러스터와 상호작용할 수 있습니다. 만약 로컬에서 Minikube, Kind, 또는 외부 클러스터를 사용 중이라면, 해당 클러스터와 통신하기 위한 `kubeconfig` 파일이 필요합니다.

- 예시: Minikube 클러스터에서 `kubectl`을 사용하려면 먼저 Minikube를 시작한 후 `kubectl`을 통해 클러스터에 명령을 내립니다.

```bash
minikube start
kubectl get pods
```

이제 `kubectl`을 설치했으므로, Kubernetes 클러스터를 관리하는 데 사용할 수 있습니다.



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