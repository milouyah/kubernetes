# [컨테이너 인프라 환경 구축을 위한 쿠버네티스/도커](http://www.kyobobook.co.kr/product/detailViewKor.laf?barcode=9791165215743)

* [github](https://github.com/sysnet4admin/_Book_k8sInfra)

# 1장 새로운 인프라 환경이 온다
## 1.1 컨테이너 인프라 환경이란
## 1.2 컨테이너 인프라 환경을 지원하는 도구
* 베이그란트, 도커, 쿠버네티스, 젠킨스, 프로메테우스, 그라파나
## 1.3 새로운 인프라 환경의 시작

# 2장 테스트 환경 구성하기

* 코드형 인프라 (IaC, Intrastructure as Code) - [vagrant](https://github.com/milouyah/vagrant)

## 2.1 테스트 환경을 자동으로 구성하는 도구
## 2.2 베이그런트로 테스트 환경 구축하기
## 2.3 터미널 프로그램으로 가상 머신 접속하기


1. [VirtualBox](https://www.virtualbox.org/)
2. [Vagrant](https://www.vagrantup.com/)


# [3장 컨테이너를 다루는 표준 아키텍처, 쿠버네티스](./ch3/README.md)
# [4장 쿠버네티스를 이루는 컨테이너 도우미, 도커](./ch4/README.md)

# 5장 지속적 통합과 배포 자동화, 젠킨스
5.1 컨테이너 인프라 환경에서 CI/CD
5.2 젠킨스 설치를 위한 간편화 도구 살펴보기
5.3 젠킨스 설치 및 설정하기
5.4 젠킨스로 CI/CD 구현하기
5.5 젠킨스 플러그인을 통해 구현되는 GitOps

# 6장 안정적인 운영을 완성하는 모니터링, 프로메테우스와 그라파나
6.1 컨테이너 인프라 환경 모니터링하기
6.2 프로메테우스로 모니터링 데이터 수집과 통합하기
6.3 PromQL로 메트릭 데이터 추출하기
6.4 그라파나로 모니터링 데이터 시각화하기
6.5 좀 더 견고한 모니터링 환경 만들기

부록 A kubectl을 더 쉽게 사용하기
부록 B 쿠버 대시보드 구성하기
부록 C kubespray로 쿠버네티스 자동 구성하기
부록 D 컨테이너 깊게 들여다보기

