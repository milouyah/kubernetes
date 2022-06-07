# CHAPTER 01 컨테이너와 쿠버네티스
## 1.1 컨테이너 기술의 개요
* 컨테이너란?
* 컨테이너 애플리케이션 개발의 흐름

## 1.2 쿠버네티스의 개요

* Kubernets ~ multihost 환경에서의 container 관리

<br><br>

### 분산 환경에서 컨테이너 운용 관리
*  쿠버네티스, 도커, Apache Mesos/Marathon
*  
### 쿠버네티스의 특징
* 여러 서버에서 컨테이너 관리
* 컨테이너 배포
* 컨테이너간 네트워크 관리
* 컨테이너 부하 분산
* 컨테이너 감사
* 컨테이너 업데이트
* 장애 발생 시 자동 복구

#### 실현
* 선언적 설정과 API 센트릭
* '시스템이 원래 되어 있어야 할 모습'을 정의 파일에 설정(선언적 설정)하여 장애가 발생해도 사람이 개입하지 않고 수습

#### Cloud Native Computing Foundation
* Fluendd 로그 콜렉터
* gRPC RPC 프레임 워크
* Envoy 서비스 프록시
* containerd 컨테이너 런타임


### 쿠버네티스의 도입
* EKS (Amaznon Elastic Container Service for K8S)
* GKE
* AKS (Azure K8S Service)

### 쿠버네티스의 유스케이스

https://azure.microsoft.com/ko-kr/services/kubernetes-service/
