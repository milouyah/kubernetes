# Tools
## [Kubectl](./kubectl/README.md)
## [Kind](./kind/README.md)
## [Minikube](./minikube/README.md)

## Monitoring
* `수집`->`통합`->`시각화`
### [Prometheus](./prometheus/README.md)
### [Grafana](./grafana/README.md)
### [Kibana(for Elastic Search)](./kibana/README.md)\


## Local K8S
로컬 PC에서 Kubernetes를 사용하기에 적합한 툴로는 다음과 같은 옵션들이 있습니다:

1. **Minikube**: 가장 인기 있는 로컬 Kubernetes 클러스터 관리 도구입니다. 로컬에서 Kubernetes 클러스터를 실행할 수 있도록 도와주며, 다수의 하이퍼바이저(예: VirtualBox, Hyper-V, Docker)를 지원합니다.

2. **Kind (Kubernetes IN Docker)**: Docker 컨테이너 안에서 Kubernetes 클러스터를 실행할 수 있게 해주는 도구입니다. 매우 가볍고, 테스트 환경에서 자주 사용됩니다.

3. **Rancher Desktop**: Kubernetes를 로컬에서 실행할 수 있게 도와주며, Docker와 함께 통합하여 사용할 수 있습니다. GUI 기반 관리 기능도 제공하여 사용이 편리합니다.

4. **k3s**: 경량 Kubernetes 배포판으로 리소스가 적은 환경에서 Kubernetes를 실행할 수 있게 해줍니다. 로컬 개발 환경에서 빠르게 설정하고 테스트할 수 있습니다.

5. **Docker Desktop**: Docker Desktop에는 Kubernetes 클러스터를 로컬에서 실행할 수 있는 옵션이 기본으로 포함되어 있어, Docker와 Kubernetes를 함께 사용할 수 있습니다.

이 도구들은 로컬에서 Kubernetes를 쉽게 사용할 수 있게 해주며, 개발 및 테스트 용도로 적합합니다.
