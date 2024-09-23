Kubernetes에서 **로컬 이미지를 실행**하려고 할 때 `ImagePullBackOff` 오류가 발생하는 이유는 Kubernetes 노드에서 이미지를 찾지 못하거나, 기본적으로 로컬 이미지를 사용하지 않기 때문입니다. Kubernetes는 기본적으로 Docker Hub 또는 다른 컨테이너 레지스트리에서 이미지를 가져오려고 시도합니다.

로컬 이미지를 Kubernetes에서 실행하려면 몇 가지 설정이 필요합니다.

### 1. **로컬 클러스터 사용 여부 확인**
로컬 이미지를 사용하려면 **로컬 클러스터** (예: `minikube`, `kind`, `k3s`)에서 Kubernetes를 실행 중이어야 합니다. 만약 Kubernetes 클러스터가 클라우드에서 실행 중인 경우, 노드가 로컬 이미지를 인식하지 못할 수 있습니다.

#### **Minikube를 사용하는 경우:**

Minikube에서 로컬 이미지를 사용하려면 `minikube`의 Docker 데몬을 사용해야 합니다. 다음 명령을 사용하여 Minikube 클러스터의 Docker 데몬에 접근합니다:

```bash
eval $(minikube docker-env)
```

이 명령을 사용하면 현재 터미널 세션에서 Minikube의 Docker 데몬을 사용하여 이미지를 빌드할 수 있습니다. 이제 로컬 이미지를 다시 빌드한 후 Kubernetes에서 사용할 수 있습니다:

```bash
docker build -t <image-name> .
```

빌드한 후, Kubernetes에서 해당 이미지를 실행할 수 있습니다.

```bash
kubectl run my-app --image=<image-name>
```

### 2. **`imagePullPolicy`를 `Never`로 설정**

로컬 이미지를 사용할 때, Kubernetes는 기본적으로 외부 레지스트리에서 이미지를 가져오려고 하기 때문에 `ImagePullBackOff` 오류가 발생합니다. 이를 방지하려면 `imagePullPolicy`를 `Never`로 설정하여 Kubernetes가 이미지를 로컬에서 찾도록 해야 합니다.

#### A. **kubectl run 명령으로 실행하는 경우:**

```bash
kubectl run my-app --image=<image-name> --image-pull-policy=Never
```

#### B. **Deployment 파일을 사용하는 경우:**

`yaml` 파일에서 `imagePullPolicy`를 `Never`로 설정합니다.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: <image-name>
        imagePullPolicy: Never
        ports:
        - containerPort: <port>
```

이 설정을 통해 Kubernetes는 외부 레지스트리에서 이미지를 풀링하지 않고, 로컬에 있는 이미지를 사용하게 됩니다.

### 3. **Kind 클러스터를 사용하는 경우**

`kind`를 사용하고 있다면 `kind` 클러스터 내의 Docker 데몬에 이미지를 로드해야 합니다. `kind load` 명령을 사용하여 클러스터에 이미지를 로드할 수 있습니다.

```bash
kind load docker-image <image-name>
```

이 명령을 사용한 후, Kubernetes에서 해당 이미지를 실행할 수 있습니다.

### 4. **이미지가 실제로 노드에 있는지 확인**

Kubernetes가 이미지를 찾을 수 없을 때 발생할 수 있으므로, 다음 명령어로 이미지가 클러스터 노드에서 제대로 빌드되었는지 확인하세요.

```bash
docker images
```

이미지가 목록에 있으면 올바르게 빌드된 것입니다. 이 확인을 통해 문제가 이미지 이름 오타 등에서 발생한 것인지 점검할 수 있습니다.

### 5. **로그 확인**

Pod의 상태가 `ImagePullBackOff`인 경우, 다음 명령을 통해 상세한 로그를 확인할 수 있습니다:

```bash
kubectl describe pod <pod-name>
```

이 명령을 통해 Pod가 이미지를 가져오지 못하는 이유를 확인하고, 설정을 수정할 수 있습니다.

---

이 방법들을 통해 로컬 이미지를 Kubernetes에서 실행할 때 발생하는 `ImagePullBackOff` 문제를 해결할 수 있습니다.