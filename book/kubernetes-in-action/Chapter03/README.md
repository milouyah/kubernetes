# [Pods](../../../architecture/pods/README.md)

# 3장. 파드: 쿠버네티스에서 컨테이너 실행

## 3.1 파드 소개
3.1.1 파드가 필요한 이유
3.1.2 파드 이해하기
3.1.3 파드에서 컨테이너의 적절한 구성

## 3.2 YAML 또는 JSON 디스크립터로 파드 생성
### 3.2.1 기존 파드의 YAML 디스크립터 살펴보기
```bash
kubectl get po [pod-name] -o yaml
```

* Metadata
* Spec
* Status




### 3.2.2 파드를 정의하는 간단한 YAML 정의 작성하기
### 3.2.3 kubectl create 명령으로 파드 만들기
### 3.2.4 애플리케이션 로그 보기
### 3.2.5 파드에 요청 보내기

## 3.3 레이블을 이용한 파드 구성
3.3.1 레이블 소개
3.3.2 파드를 생성할 때 레이블 지정
3.3.3 기존 파드 레이블 수정

## 3.4 레이블 셀렉터를 이용해 파드 부분 집합 나열
3.4.1 레이블 셀렉터를 사용한 파드 나열
3.4.2 레이블 셀렉터에서 여러 조건 사용

## 3.5 레이블과 셀렉터를 이용해 파드 스케줄링 제한
3.5.1 워커 노드 분류에 레이블 사용
3.5.2 특정 노드에 파드 스케줄링
3.5.3 하나의 특정 노드로 스케줄링

## 3.6 파드에 어노테이션 달기
3.6.1 오브젝트의 어노테이션 조회
3.6.2 어노테이션 추가 및 수정

## 3.7 네임스페이스를 사용한 리소스 그룹화
3.7.1 네임스페이스의 필요성
3.7.2 다른 네임스페이스와 파드 살펴보기
3.7.3 네임스페이스 생성
3.7.4 다른 네임스페이스의 오브젝트 관리
3.7.5 네임스페이스가 제공하는 격리 이해

## 3.8 파드 중지와 제거
3.8.1 이름으로 파드 삭제
3.8.2 레이블 셀렉터를 이용한 파드 삭제
3.8.3 네임스페이스를 삭제한 파드 제거
3.8.4 네임스페이스를 유지하면서 네임스페이스 안에 있는 모든 파드 삭제
3.8.5 네임스페이스에서 (거의) 모든 리소스 삭제
3.9 요약