Minikube 내부로 파일을 복사하는 방법은 `minikube cp` 명령을 사용하여 로컬 시스템에서 Minikube 클러스터의 가상 머신 또는 컨테이너 내부로 파일을 전송할 수 있습니다.

### **Minikube에 파일 복사하는 방법**

`minikube cp` 명령을 사용하면 로컬 파일을 Minikube의 VM이나 Docker 환경으로 쉽게 복사할 수 있습니다.

#### **명령어 형식**

```bash
minikube cp <source-file-path> <destination-path-in-minikube>
```

- `<source-file-path>`: 로컬 시스템에 있는 파일의 경로
- `<destination-path-in-minikube>`: Minikube VM이나 Docker 환경에서 파일을 복사할 목적지 경로

#### **예시: 인증서 파일을 복사하는 경우**

예를 들어, 로컬에 있는 `ca.crt` 인증서를 Minikube VM 내 `/etc/docker/certs.d/my-registry.com/` 디렉토리로 복사하려면 다음 명령을 사용할 수 있습니다:

```bash
minikube cp /path/to/ca.crt /etc/docker/certs.d/my-registry.com/ca.crt
```

이 명령을 실행하면 `ca.crt` 파일이 Minikube 내부의 해당 경로로 복사됩니다.

### **Minikube 내부에서 파일 확인**

파일을 복사한 후, Minikube 내부에서 파일이 올바르게 복사되었는지 확인하려면 `minikube ssh` 명령을 사용하여 Minikube VM 내부에 접속할 수 있습니다.

```bash
minikube ssh
```

접속한 후 복사한 경로로 이동하여 파일이 존재하는지 확인할 수 있습니다.

```bash
ls /etc/docker/certs.d/my-registry.com/
```

### **기타 예시**

#### 1. **로컬 파일을 Minikube의 `/home/docker/` 디렉토리로 복사**
```bash
minikube cp ./my-local-file.txt /home/docker/my-local-file.txt
```

#### 2. **Minikube에서 복사한 파일을 Docker에서 사용**

복사한 인증서 또는 다른 파일을 Docker 컨테이너에서 사용하려면 Minikube 내 Docker 데몬을 재시작해야 할 수 있습니다.

```bash
sudo systemctl restart docker
```

---

이렇게 하면 `minikube cp` 명령을 사용하여 로컬 파일을 Minikube 내부로 복사할 수 있으며, 필요 시 Docker 환경에서도 해당 파일을 사용할 수 있습니다.


#
eval $(minikube docker-env)
docker build -t my-image .