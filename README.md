# 삶의 방향
_"세상을 넓게 바라보고 사람을 깊이있게 이해하자"_
<br> <br> 많이 서투르더라도 나의 길을 걸어가자
<hr> 

## 대표 프로젝트 
(아래의 목표에 맞춰 진행 중)
| 이때까지의 경험과 지식을 하나에 담은 질의응답 시스템 |
| - |
| <strong>1. medical-qna-client</strong> (2024.07 ~ 현재) <br> &nbsp;-&nbsp;&nbsp;목적: 시스템 실시간 모니터링, 성능 테스트 시행 & 결과 보고서 작성 <br> &nbsp;-&nbsp;&nbsp;목표: 객체지향 설계, 병렬 프로그래밍, JavaFX와 Spring 결합 (DI와 IoC, 이벤트 기반 아키텍처 적용) <br> &nbsp;-&nbsp;&nbsp;기술: RSocket, Spring Boot, JavaFX |
| <strong>2. medical-qna-monitor</strong> (2024.07 ~ 현재) <br> &nbsp;-&nbsp;&nbsp;목적: 시스템 자원, 로그  모니터링 서버 <br> &nbsp;-&nbsp;&nbsp;목표: 비동기 데이터 스트림, 리액티브 프로그래밍 <br> &nbsp;-&nbsp;&nbsp;기술: RSocket, RabbitMQ |
| <strong>3. medical-qna-gateway</strong> (2024.07 ~ 현재) <br> &nbsp;-&nbsp;&nbsp;목적: my-health-server에 대한 API server, 로드밸런서 <br> &nbsp;-&nbsp;&nbsp;목표: 분산 성능 측정 <br> &nbsp;-&nbsp;&nbsp;기술:  Spring Cloud Gateway, Redis, RabbitMQ |
| <strong>4. my-health-ap-server</strong> (2024.02 ~ 현재) <br> &nbsp;-&nbsp;&nbsp;목적: 질의 응답, 회원 관리 AP Server <br> &nbsp;-&nbsp;&nbsp;목표: 멀티 인스턴스 분산, 동시성 처리, (육각형 아키텍처를 활용한) 영속성 계층 전환 등의 성능 테스트 <br> &nbsp;-&nbsp;&nbsp;기술: Spring WebMVC, JPA, MyBatis, MongoDB, Redis, RabbitMQ, Spring Actuator |
| <strong>5. my-health-webflux-server</strong> (2024.07 ~ 현재) <br> &nbsp;-&nbsp;&nbsp;목적: 리액티브 프로그래밍으로 기존 서버 전환 <br> &nbsp;-&nbsp;&nbsp;목표: 기존의 동기 블로킹 서버와 성능 비교 <br> &nbsp;-&nbsp;&nbsp;기술: Spring WebMVC -> Spring WebFlux |
| <strong>6. symptom-similarity-service</strong> (2024.06 ~ 중단) <br> &nbsp;-&nbsp;&nbsp;목적: SBERT와 지식 그래프를 활용한 의미론적 검색 |
|테스트 목표: JUnit 5, Mockito, Spring Boot Test, Spring WebMVC Test, Spring WebFlux Test, Spring Data JPA Test, Spring Data Redis Test |

<br>

---

# 기타 진행한 프로젝트
<details>
  <summary> 2022.07 ~ 2022.08 : 우회 비속어 필터링 <br> &nbsp;&nbsp;&nbsp; 새로운 시도 : 직접 벡터 표현 </summary>

|항목| 내용|
|----|-----|
|목표|벡터에 대한 이해|
|개요| 비속어 집합 내 단어와 유사한 우회 표현 탐지 모듈 개발|
|핵심 내용| 1) 모양이 유사한 음소, 기호, 숫자 등을 유사한 벡터로 표현 <br> 2) 학습 모델을 활용하지 않고 직접 벡터로 표현<br>3) 코사인 유사도로 비속어 유사도 판단|
|예시| [1, 0.5, 0.5, 0.5, 0, 0, 0,  ..., 0] -> ㅇ <br> [0.5, 1, 0.5, 0.5, 0, 0, 0,  ..., 0] -> 0|
</details>

<details>
  <summary> 2023.02 ~ 2023.11 : 학대 피해 아동 감정 모니터링 <br> &nbsp;&nbsp;&nbsp; 새로운 시도 : ICT 멘토링, 팀장, 실시간 다중 채팅 서버, MSA, Docker, Notion </summary>

|항목| 내용|
|----|-----|
|목표| 자연어 처리 학습 모델을 활용해서 사회에 도움이 되는 팀 프로젝트 기획, 개발, 협업 |
|개요| - 아동<br> chat gpt 모델과 채팅 <br><br> - 전문가<br> 감성 분석 모델이 아동의 채팅을 분석한 결과를 모니터링<br> 필요시 아동과 채팅 상담|
|수행 내용| 1) MSA 고려한 백엔드 설계 <br> 2) NestJS, Flask 활용하여 서버 구현 <br> 3) Redis, Socket.io 활용하여 다중 채팅 서버 구현 <br> 4) Docker로 컨테이너 이미지 빌드 |
|서버<br>(서비스)| 메인 서버(API 서버), 감성 분석 서버, 챗봇 채팅 서버, 아동과 전문가 채팅 서버|
|언어| TypeScript, JavaScript, Python|
|기타| MySQL, TypeORM, Notion, GitLab|
</details>

<details>
  <summary> 2023.07 ~ 2023.08 : 원초적 검색기 <br> &nbsp;&nbsp;&nbsp; 새로운 시도 : indexing, querying, ranking </summary>

|항목| 내용|
|----|-----|
|목표|검색엔진에 대한 이해|
|개요| 형태소를 바탕으로 검색하는 원초적인 검색기 |
|수행 내용| 1) indexing: 문서 테이블과 형태소 기반 역색인 테이블에 저장 <br> 2) querying: 형태소 기반으로 사용자 검색 문장(쿼리) 분석 <br> 3) ranking: 찾은 문서들 중 TF-IDF와 벡터 거리 계산으로 사용자 쿼리와 관련도 계산|
|서버<br>(서비스)| 메인 서버, 형태소 분석 서버, ranking 서버|
|언어| TypeScript, Python|
|기타| NestJS, Flask, MySQL|
|참고 도서|'검색을 위한 딥러닝' 토마소 테오필리 저|
</details>

<details>
  <summary> 2023.12 ~ 2024.02 : 검색기 개선 및 운영 <br> &nbsp;&nbsp;&nbsp; 새로운 시도 : 스터디, 컨테이너 오케스트레이션, SBERT, Apache JMeter, Prometheus, Grafana, Jira </summary>

|항목| 내용|
|----|-----|
|목표|안정적 서버 운용|
|개요| 1) 기존 원초적 검색기에 SBERT 적용 <br> 2) 가용성을 위한 컨테이너 운영, 모니터링, 부하 테스트 <br> 2) 스터디식으로 공유(Jira, Notion)|
|수행 내용| 1) SBERT: 사용자 쿼리와 문서를 TF-IDF가 아닌 문맥 의미로 임베딩 <br> 2) 컨테이너: 도커로 이미지 빌드, Rancher Desktop로 운영 <br> 3) 모니터링: Prometheus, Grafana로 메트릭 모니터링 <br> 4) 부하 테스트: Apache JMeter로 사용자 요청 테스트 <br> 5) 스터디: 다양한 관심 분야(NLP, 컨테이너 등), 프로젝트 진행 상황 공유 |
|참고 도서|'쿠버네티스 교과서' 엘튼 스톤맨 저|
</details>
