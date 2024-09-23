Minikube 환경에서 Docker 이미지를 빌드할 때 **x509** 오류가 발생하는 경우, 이는 인증서 관련 문제로 인해 발생하는 경우가 많습니다. 특히, 로컬 시스템과 Minikube 클러스터 간에 Docker 환경을 제대로 설정하지 않았거나, 네트워크 또는 프록시 문제로 인해 SSL 인증서가 유효하지 않을 수 있습니다. 아래에 이 문제를 해결하기 위한 몇 가지 방법을 제시하겠습니다.

### 1. **Minikube Docker 환경 설정**
Minikube의 Docker 데몬을 사용하여 이미지를 빌드할 때, **로컬 Docker 데몬**이 아닌 **Minikube 내의 Docker 데몬**을 사용해야 합니다. 이를 위해 `minikube docker-env` 명령을 사용하여 Minikube의 Docker 환경을 로컬 환경에 설정해야 합니다.

```bash
eval $(minikube docker-env)
```

이 명령은 현재 터미널 세션에서 Minikube의 Docker 데몬을 사용하도록 설정합니다. 설정 후에는 Minikube 내에서 Docker 이미지를 빌드하고, Kubernetes에서 이 이미지를 사용할 수 있습니다.

#### 빌드 예시:
```bash
docker build -t my-image .
```

이렇게 하면 Minikube 내의 Docker 데몬을 사용하여 이미지를 빌드하게 되며, 이후 Kubernetes에서 이를 실행할 수 있습니다.

### 2. **Minikube 인증서 문제 해결 (x509 오류)**
`x509` 오류는 인증서 문제에서 발생합니다. 이를 해결하려면 Docker가 SSL을 적절하게 처리할 수 있도록 인증서 관련 설정을 수정해야 할 수 있습니다.

#### a. **SSL 검증 비활성화 (임시 해결책)**

Docker에서 SSL 검증을 비활성화하여 문제를 일시적으로 해결할 수 있습니다. 이 방법은 보안적 문제가 있기 때문에 개발 환경에서만 사용하고, 프로덕션 환경에서는 적절한 인증서 설정을 권장합니다.

```bash
docker build --tls-verify=false -t my-image .
```

#### b. **Minikube CA 인증서 수동 설정**

Minikube에서 사용되는 인증서를 Docker에 수동으로 설정할 수도 있습니다. 인증서가 손상되었거나 누락된 경우, Minikube 인증서를 다시 설정할 수 있습니다. 

먼저, Minikube가 사용하는 인증서를 확인하고, 이를 Docker가 신뢰하도록 설정합니다. 다음 명령으로 인증서를 확인하세요:

```bash
minikube ssh cat /etc/docker/certs.d/<registry>/ca.crt
```

이 인증서를 로컬 Docker의 인증서로 추가하거나 갱신할 수 있습니다.

### 3. **Docker 데몬의 SSL 설정 수정**

Docker 데몬이 올바르게 SSL을 처리하지 못할 때 인증서 오류가 발생할 수 있습니다. Minikube의 Docker 데몬이 올바르게 설정되어 있는지 확인해보세요.

```bash
minikube ssh
```

Minikube 내부에서 `/etc/docker/` 경로를 확인하여 올바른 인증서가 존재하는지, 그리고 인증서 파일이 유효한지 확인합니다.

### 4. **Minikube 재설정**

Minikube 자체의 설정 문제가 있을 수 있으므로, Minikube를 재설정하여 문제를 해결할 수 있습니다. 다음 명령을 사용해 Minikube를 초기화하고 재시작하세요.

```bash
minikube delete
minikube start
```

Minikube를 다시 시작한 후, Docker 환경을 다시 설정하고 이미지를 빌드해보세요:

```bash
eval $(minikube docker-env)
docker build -t my-image .
```

### 5. **프록시 설정 확인**

회사나 학교의 네트워크에서 SSL 프록시를 사용할 경우, Docker나 Minikube가 외부 레지스트리에 접근할 때 SSL 인증 문제가 발생할 수 있습니다. 이 경우, 프록시 설정을 확인하고 Docker 및 Minikube의 프록시 설정을 올바르게 구성해야 합니다.

#### Docker의 프록시 설정:

Docker 데몬에 프록시 설정을 추가합니다. `/etc/systemd/system/docker.service.d/`에 환경 변수를 추가하여 프록시 설정을 적용할 수 있습니다.

```ini
[Service]
Environment="HTTP_PROXY=http://proxy.example.com:8080/"
Environment="HTTPS_PROXY=https://proxy.example.com:8080/"
Environment="NO_PROXY=localhost,127.0.0.1,.example.com"
```

#### Minikube의 프록시 설정:

프록시 설정이 필요한 경우, Minikube 시작 시 프록시 설정을 포함하여 시작할 수 있습니다.

```bash
minikube start --docker-env HTTP_PROXY=http://proxy.example.com:8080 --docker-env HTTPS_PROXY=https://proxy.example.com:8080
```

프록시 설정이 완료되면 다시 이미지를 빌드하고 테스트해보세요.

### 요약

- `eval $(minikube docker-env)` 명령으로 Minikube의 Docker 데몬을 사용.
- `x509` 인증서 오류가 발생할 경우, SSL 검증을 비활성화하거나 인증서를 확인.
- Minikube 및 Docker의 프록시 설정을 점검.
- Minikube를 초기화하거나 재설정하여 문제를 해결.

위의 방법들 중 하나를 통해 `x509` 오류 문제를 해결하고 Docker 이미지를 성공적으로 빌드할 수 있을 것입니다.