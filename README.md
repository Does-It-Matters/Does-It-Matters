# 삶의 방향
_"세상을 넓게 바라보고 사람을 깊이있게 이해하자"_
<br> <br> 많이 서투르더라도 나의 길을 걸어가자
<hr> 

<!--
|          | 목표                                                                                   |
| -------- | ------------------------------------------------------------------------------------- |
| 학습      | 해보면서 배우자!                                                                         |
| 협업      | 적극적인 코드 리뷰, JavaDoc으로 문서화, 깃허브(위키, 이슈, 프로젝트)로 진행 과정 공유                |
| PM       | 프로젝트의 진행 상황과 방향에 대한 팀원들 이해 동기화, 서로에 대한 이해도 향상, 프로젝트 간 일정 관리     |
| 설계 전환  | 전통적 모놀리식 설계, 모듈러 모놀리식 설계, MSA 전환                                            |
| 트랜잭션   | 락, MVCC, 격리수준에 대한 다양한 시도와 성능 측정                                              |
| DB 전환   | 육각형 아키텍처와 saga 패턴으로 손쉽게 MySQL(JPA <-> MyBatis) <-> MongoDB 전환                 |
| 코드 검증  | 단위 테스트와 통합 테스트들을 활용하여 품질 보장                                                |
| CI/CD    | 마이크로서비스에 적용                                                                      |
| 성능 체크  | 부하테스트에 대한 결과 보고서 작성                                                           |
| 모니터링   | 리소스와 로그에 대해 수집, 전송, 가공, 표현                                                   |
--> 

# 2024년 스토리라인 
## [MSA 질의응답 시스템 (24년 11월 ~ 현재)](https://github.com/orgs/Micro-Answer/repositories)
### 5. Backend
- 기존의 모놀리식 QnA 서버에서 MSA로의 전환에 대한 다양한 경험을 위해 기획
- 일반 유저 서비스  [general-service](https://github.com/Micro-Answer/msa-general-service) 개발 담당 

### 6. Frontend (예정)
- 기존의 게시판 클라이언트를 정리하여 다시 개발
- JavaFX와 Spring을 활용하여 결합도를 줄이고 응집도 향상 목표
<br>

## Monolithic 질의응답 시스템 (24년 7월 ~ 24년 9월)
### 3. 모놀리식 QnA 서버 - [자세한 내용은 깃허브 wiki](https://github.com/Does-It-Matters/my-health-block-ap-server/wiki)
- 기존에 개발된 블록체인 관련 서버를 학습용으로 축소한 버전
- 최소한의 질의응답 서비스 제공
- 육각형 아키텍처 개선
- 멀티 모듈로 분리 - 인터페이스 모듈, 구현체 모듈, 출력 어댑터 모듈 분리 등
- 이후 MSA 전환

### 4. 게시판 클라이언트 - [자세한 내용은 깃허브 wiki](https://github.com/Does-It-Matters/medical-qna-client/wiki)
- 게시판을 이용할 수 있는 클라이언트 개발
- 결합도를 줄인 아키텍처, 디자인 설계
- 응집도를 높이기 위한 멀티 모듈 도입
- JavaFX에 Spring DI, IoC를 도입하여 의존성 감소
- Spring Framework의 이벤트를 도입하여 순환 참조 완화
- Spring RSocket 등 Spring Framework로 개발 생산성 향상
- 로그 및 리소스 실시간 모니터링(중단)
- 부하 테스트 수행 및 결과 보고서 작성(중단)
<br>

## 블록체인 활용 의료 관리 시스템 (24년 2월 ~ 24년 6월)
### 1. 기획 
- 환자가 본인의 데이터를 소유, 제공, 관리
- 의료 관련 질의응답
- 질의응답에서 RAG 활용하여 개인 맞춤형 설명 (실제 구현 x)

### 2. 백엔드
- 처음으로 스프링 부트를 활용하여 서버 개발
- 의료진, 환자로 나누어 회원 관리 개발
- 질의응답 기능 개발
<br>

---

### 이전 스토리 라인 - 2022년 ~ 2024년 초
1. 2022.07 ~ 2022.08 : [우회 비속어 필터링 모듈 개발](https://github.com/orgs/bad-word-filter/repositories)
<br> 새로운 시도 : 파이썬, 직접 벡터 표현
<!--
목표: 벡터에 대한 이해
개요: 비속어 집합 내 단어와 유사한 우회 표현 탐지 모듈 개발
핵심 내용: 1) 모양이 유사한 음소, 기호, 숫자 등을 유사한 벡터로 표현 <br> 2) 학습 모델을 활용하지 않고 직접 벡터로 표현<br>3) 코사인 유사도로 비속어 유사도 판단
예시: [1, 0.5, 0.5, 0.5, 0, 0, 0,  ..., 0] -> ㅇ <br> [0.5, 1, 0.5, 0.5, 0, 0, 0,  ..., 0] -> 0
-->

2. 2023.02 ~ 2023.11 : [학대 피해 아동 감정 모니터링 sw 개발](https://github.com/orgs/hope-chat/repositories)
<br> 새로운 시도 : ICT 멘토링, 팀장, 실시간 다중 채팅 서버, NestJS, Redis, Socket.io, MSA, Docker, Notion
<!--
목표: 자연어 처리 학습 모델을 활용해서 사회에 도움이 되는 팀 프로젝트 기획, 개발, 협업
개요: - 아동<br> chat gpt 모델과 채팅 <br><br> - 전문가<br> 감성 분석 모델이 아동의 채팅을 분석한 결과를 모니터링<br> 필요시 아동과 채팅 상담
수행 내용: 1) MSA 고려한 백엔드 설계 <br> 2) NestJS, Flask 활용하여 서버 구현 <br> 3) Redis, Socket.io 활용하여 다중 채팅 서버 구현 <br> 4) Docker로 컨테이너 이미지 빌드
서버<br>(서비스): 메인 서버(API 서버), 감성 분석 서버, 챗봇 채팅 서버, 아동과 전문가 채팅 서버
언어: TypeScript, JavaScript, Python
기타: MySQL, TypeORM, Notion, GitLab
-->

3. 2023.07 ~ 2023.08 : [원초적 검색기 개발](https://github.com/orgs/simple-search-engine/repositories)
<br> 새로운 시도 : indexing, querying, ranking
<!--
목표: 검색엔진에 대한 이해
개요: 형태소를 바탕으로 검색하는 원초적인 검색기
수행 내용: 1) indexing: 문서 테이블과 형태소 기반 역색인 테이블에 저장 <br> 2) querying: 형태소 기반으로 사용자 검색 문장(쿼리) 분석 <br> 3) ranking: 찾은 문서들 중 TF-IDF와 벡터 거리 계산으로 사용자 쿼리와 관련도 계산
서버<br>(서비스): 메인 서버, 형태소 분석 서버, ranking 서버
언어: TypeScript, Python
기타: NestJS, Flask, MySQL
참고 도서: '검색을 위한 딥러닝' 토마소 테오필리 저
-->

4. 2023.12 ~ 2024.02 : [검색기 개선 및 운영 스터디](https://github.com/orgs/simple-search-engine/repositories)
<br> 새로운 시도 : 스터디, 컨테이너 오케스트레이션, 의미론적 검색, Apache JMeter, Prometheus, Grafana, Jira
<!--
목표: 안정적 서버 운용
개요: 1) 기존 원초적 검색기에 SBERT 적용 <br> 2) 가용성을 위한 컨테이너 운영, 모니터링, 부하 테스트 <br> 2) 스터디식으로 공유(Jira, Notion)
수행 내용: 1) SBERT: 사용자 쿼리와 문서를 TF-IDF가 아닌 문맥 의미로 임베딩 <br> 2) 컨테이너: 도커로 이미지 빌드, Rancher Desktop로 운영 <br> 3) 모니터링: Prometheus, Grafana로 메트릭 모니터링 <br> 4) 부하 테스트: Apache JMeter로 사용자 요청 테스트 <br> 5) 스터디: 다양한 관심 분야(NLP, 컨테이너 등), 프로젝트 진행 상황 공유
참고 도서: '쿠버네티스 교과서' 엘튼 스톤맨 저
-->
