# [5장. 서비스: 클라이언트가 파드를 검색하고 통신을 가능하게 함]()

5.1 서비스 소개
5.1.1 서비스 생성
5.1.2 서비스 검색
5.2 클러스터 외부에 있는 서비스 연결
5.2.1 서비스 엔드포인트 소개
5.2.2 서비스 엔드포인트 수동 구성
5.2.3 외부 서비스를 위한 별칭 생성
5.3 외부 클라이언트에 서비스 노출
5.3.1 노드포트 서비스 사용
5.3.2 외부 로드밸런서로 서비스 노출
5.3.3 외부 연결의 특성 이해
5.4 인그레스 리소스로 서비스 외부 노출
5.4.1 인그레스 리소스 생성
5.4.2 인그레스로 서비스 액세스
5.4.3 하나의 인그레스로 여러 서비스 노출
5.4.4 TLS 트래픽을 처리하도록 인그레스 구성
5.5 파드가 연결을 수락할 준비가 됐을 때 신호 보내기
5.5.1 레디니스 프로브 소개
5.5.2 파드에 레디니스 프로브 추가
5.5.3 실제 환경에서 레디니스 프로브가 수행해야 하는 기능
5.6 헤드리스 서비스로 개별 파드 찾기
5.6.1 헤드리스 서비스 생성
5.6.2 DNS로 파드 찾기
5.6.3 모든 파드 검색 - 준비되지 않은 파드도 포함
5.7 서비스 문제 해결
5.8 요약