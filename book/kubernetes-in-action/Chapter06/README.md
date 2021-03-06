# 6장. 볼륨: 컨테이너에 디스크 스토리지 연결

## 6.1 볼륨 소개
6.1.1 예제의 볼륨 설명
6.1.2 사용 가능한 볼륨 유형 소개

## 6.2 볼륨을 사용한 컨테이너 간 데이터 공유
6.2.1 emptyDir 볼륨 사용
6.2.2 깃 리포지터리를 볼륨으로 사용하기

## 6.3 워커 노드 파일시스템의 파일 접근
6.3.1 hostPath 볼륨 소개
6.3.2 hostPath 볼륨을 사용하는 시스템 파드 검사하기

## 6.4 퍼시스턴트 스토리지 사용
6.4.1 GCE 퍼시스턴트 디스크를 파드 볼륨으로 사용하기
6.4.2 기반 퍼시스턴트 스토리지로 다른 유형의 볼륨 사용하기

## 6.5 기반 스토리지 기술과 파드 분리
6.5.1 퍼시스턴트볼륨과 퍼시스턴트볼륨클레임 소개
6.5.2 퍼시스턴트볼륨 생성
6.5.3 퍼시스턴트볼륨클레임 생성을 통한 퍼시스턴트볼륨 요청
6.5.4 파드에서 퍼시스턴트볼륨클레임 사용하기
6.5.5 퍼시스턴트볼륨과 퍼시스턴트볼륨클레임 사용의 장점 이해하기
6.5.6 퍼시스턴트볼륨 재사용

## 6.6 퍼시스턴트볼륨의 동적 프로비저닝
6.6.1 스토리지클래스 리소스를 통한 사용 가능한 스토리지 유형 정의하기
6.6.2 퍼시스턴트볼륨클레임에서 스토리지 클래스 요청하기
6.6.3 스토리지 클래스를 지정하지 않은 동적 프로비저닝
