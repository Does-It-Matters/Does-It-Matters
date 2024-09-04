# 삶의 방향
_"세상을 넓게 바라보고 사람을 깊이있게 이해하자"_
<br> <br> 많이 서투르더라도 나의 길을 걸어가자
<hr> 

## 여러 프로젝트로 구성된 질의응답 시스템 
||목표|
|-|-|
|협업| 적극적인 코드 리뷰, JavaDoc으로 문서화, 깃허브 위키로 진행 과정 공유|
|PM| 프로젝트의 진행 상황과 방향에 대한 팀원들 이해 동기화, 서로에 대한 이해도 향상, 프로젝트 간 일정 관리|
|설계| 각 계층에 대한 디자인, 스프링 DI/IoC/Event, 육각형 및 모듈화 아키텍처로 결합도 감소 및 응집도 향상|
|설계 변화| MSA 전환, 멀티 인스턴스, 병렬 프로그래밍, 비동기 프로그래밍, 동시성 처리, 영속성 계층 변화, 캐싱|
|코드 검증| JUnit, Mockito, Spring 통합 테스트들을 활용하여 품질 보장|
|성능 체크| 직접 개발한 자바 부하테스트 클라이언트로 결과 보고서 작성|
|모니터링| 리소스/로그/메트릭에 대해 수집/전송/가공/표현|
|CI/CD| 깃허브 패키지에 api, impl 라이브러리 배포, 마이크로서비스 배포|
|보안| JWT, API 서버|

### 프로젝트 구성
#### 1. medical-qna-client - [자세한 내용은 깃허브 wiki](https://github.com/Does-It-Matters/medical-qna-client/wiki)
1) <b>목적</b> (1) 애플리케이션 사용 (2) 로그 및 리소스 실시간 모니터링 (3) 부하 테스트 수행 및 결과 보고서 작성

2) <b>주요 특징</b>
<br>(1) 결합도를 줄인 아키텍처, 디자인 설계
<br>(2) 응집도를 높이기 위한 멀티 모듈
<br>(3) 블로킹 큐와 쓰레드를 활용한 병렬 프로그래밍
<br>(4) JavaFX에 Spring 도입하여 DI, IoC, 이벤트 기반 아키텍처, 개발 생산성 향상 추구
<br>(5) 실시간 데이터에 대한 효율적인 데이터 스트림 처리

#### 2. my-health-ap-server - [자세한 내용은 깃허브 wiki](https://github.com/Does-It-Matters/my-health-block-ap-server/wiki)
1) <b>목적</b> (1) 질의 응답 모놀리식 AP 서버
2) <b>주요 특징</b>
<b><br>- MSA 전환 과정!!!</b>
<br>(1) 육각형 아키텍처로 애플리케이션 계층의 독립성 확보
<br>(2) 도메인 별로 독립성 확보
<br>(3) 확보된 독립성으로 각 도메인의 애플리케이션 계층을 api, impl 두 모듈로 모듈화
<br>(4) api, impl 두 모듈을 깃허브 패키지에 CI/CD를 적용하여 배포
<b><br>(5) MSA 전환!!!</b>
<br>(6) 출력 어댑터 전환(JPA/MyBatis/MongoDB)
<br>(7) 트랜잭션 처리를 위해 Saga 패턴 적용
<br>(8) 통신 실패 대비
<br><b><br>- 기타 주요 요소!!!</b>
<br>모니터링, 테스트, 멀티 인스턴스, 동시성 처리, 캐싱

#### 3. medical-qna-monitor - [깃허브 wiki](https://github.com/Does-It-Matters/medical-qna-monitor/wiki)
1) <b>목적</b> (1) 모니터링 클라이언트에 시스템 자원, 로그 데이터를 송신하는 서버
2) <b>주요 특징</b>
<br>(1) 데이터 수집
<br>(2) 효율적인 데이터 스트림 전송

#### 4. medical-qna-gateway - [깃허브 wiki](https://github.com/Does-It-Matters/medical-qna-gateway/wiki)
1) <b>목적</b> (1) API 서버 (2) 로드밸런서 
2) <b>주요 특징</b>
<br>(1) JWT 인증 및 라우팅
<br>(2) 요청 헤더에 로그 식별자 추가하여 중앙화된 로그 모니터링
<br>(3) 수평 스케일링 처리
  
#### 5. my-health-webflux-server
1) <b>목적</b> (1) 리액티브 프로그래밍으로 기존 서버 전환
2) <b>주요 특징</b>
<br>(1) 애플리케이션 계층 모듈 재사용
<br>(2) 기존의 동기 블로킹 서버와 성능 비교
  
#### 6. symptom-similarity-service 
1) <b>목적</b> (1) 관련있는 질문을 의미론적으로 검색
2) <b>주요 특징</b>
<br>(1) RAG 시스템으로 진행 가능
3) <b>역할</b>
<br>(1) 계획, 분석, 설계, 피드백 위주로 진행
<br>(2) 개발은 다른 팀원이 담당 
---

### 기타 진행한 프로젝트
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
