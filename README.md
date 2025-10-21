# 경력기술서 (Work History)

**이현석 | Senior Backend/Platform Engineer**
- 이메일: [shiba@yeppyshiba.com](mailto:shiba@yeppyshiba.com)
- 블로그: [https://blog.yeppyshiba.com](https://blog.yeppyshiba.com)
- GitHub: [https://github.com/qlazzarus](https://github.com/qlazzarus)
- 연락처: 010-3802-8784
- 최종 수정일: 2025-10-21 (KST)

---

## 1) Summary

* 총 **18년** 경력의 백엔드/플랫폼 엔지니어. **운영 안정성, 자동화, 비용 최적화**에 강점.
* **문제의 본질을 설계 차원에서 해결**(동시성/락/트랜잭션 경계/아이템포턴시)하고, **관측·알림·포스트모텀**까지 포함한 운영 체계를 설계.
* AWS/EKS, CI/CD, 서버리스, 데이터베이스 최적화, 대규모 사용자 트래픽 대응 경험.
* 조직 상황에 맞춘 **점진적 리팩토링(스트랭글러 패턴)**, 배포 안정화, 개발 문화 정착(코드리뷰/테스트/품질 게이트) 주도.

---

## 2) 핵심 역량 (Core Competencies)

* **백엔드/플랫폼**: Kotlin, Java, PHP(Laravel), Python, JavaScript/TypeScript(Express/Nest 친화), REST/GraphQL, 설계 원칙(DI/레이어드/DDD-lite)
* **클라우드/인프라**: AWS(EKS, Lambda, EventBridge, S3, CloudFront, CloudWatch, RDS), 컨테이너/쿠버네티스, IaC 일부, 모니터링/알림
* **데이터베이스**: MySQL 8.x, PostgreSQL, SQLite, Redis, **Elasticsearch**(검색/콘텐츠)
* **아키텍처/운영**: 트랜잭션 경계, 락/동시성 제어, 아이템포턴시, 이벤트 로그, **블레이멀리스 포스트모텀**, 피처플래그/롤백, SLA/MTTR
* **프론트엔드 협업**: React/Next.js 기반 BFF/백오피스, API 설계/문서화(OpenAPI), 웹성능·캐싱 전략 협업

---

## 3) 기술 스택 (Selected)

* 언어: Kotlin, Java, PHP, Python, JavaScript/TypeScript, Ruby
* 프레임워크: Spring Boot, Laravel, Express(→Nest 아키텍처 개념 친숙), React/Next.js
* 데이터: MySQL, PostgreSQL, Redis, Elasticsearch
* 인프라: Docker, Kubernetes(EKS), Nginx, GitHub Actions, GitLab Runner, Nexus, AWS Lambda/EventBridge/S3/CloudFront/CloudWatch
* 품질/운영: Jest/JUnit, 통합·E2E 테스트, 로그/메트릭/트레이싱, Slack 알림, 포스트모텀 템플릿

---

## 4) 경력 요약 (Chronology)

* **PeopleBomb** – Lead Backend Developer (2025.07–2025.09)
* **PhotoWidget** – Lead Backend Developer (2023.11–2025.05)
* **Neople** – Team Leader (2019.04–2023.11) / Senior Backend Developer (2009.11–2017.06)
* **주식회사 모노클립** – Lead Backend Developer (2018.11–2019.03)
* **Freelancer** – Full-Stack Developer (2018.01–2018.10)
* **빗썸코리아** – Senior Backend Developer (2017.09–2017.11)
* **주식회사 지우닷컴** – Junior Backend Developer (2007.02–2009.07)

---

## 5) 대표 프로젝트 (STAR 중심 상세)

### 5.1 PeopleBomb – 로스터리/카페 대상 SaaS 유료화

* **기간/역할**: 2025.07–2025.09 / Lead Backend Developer
* **배경(S)**: 구독·결제 중심 유료화 전환 과정에서 정산·세금계산서·포인트 등 **금전 로직의 신뢰성/추적성** 요구. 외부 결제·콜백 불일치 이슈 존재.
* **과제(T)**: 동시성에 안전한 거래 흐름과 **정산/세금계산서 일관성** 확보, 배치 안정화, 운영 자동화.
* **행동(A)**:

  * 결제 금액 조건부 포인트 차감, 세금계산서 발급 제약 등 **수익화 정책 로직**을 도메인 규칙으로 분리.
  * **락 테이블 + 이벤트 로그 + 아이템포턴시 키**로 동시성 제어, 재시도·백오프·롤백 설계.
  * BO(정산/세금계산서) 화면 개선, 스케줄러 안정화, 외부 API 콜백 검증/보정 레이어 추가.
  * 정산 배포 오류 및 장애 패턴을 수집하여 **Slack 실시간 알림 + 포스트모텀 템플릿** 운영.
* **결과(R)**:

  * 유료화 가속: **월 매출 2억** 달성 기반(초기 정산·발급 안정화)으로 서비스 신뢰 회복.
  * 운영 측면 **휴면 에러(반복 장애) 감소**, 원인-대응-재발방지 액션 체계화.

---

### 5.2 PhotoWidget – 글로벌 대규모 트래픽 백엔드/플랫폼 전환

* **기간/역할**: 2023.11–2025.05 / Lead Backend Developer
* **배경(S)**: 글로벌 사용자 급증에 따른 레이턴시/안정성 이슈. Beanstalk 기반에서 **EKS 멀티 리전**으로 전환 필요. 대량 알림/검색/이미지 처리 신규 요구.
* **과제(T)**: 인프라 전환과 동시에 **배포 신뢰도, 관측, 알림**을 표준화하고, 대량 처리 컴포넌트를 안정화.
* **행동(A)**:

  * 인프라: **AWS EKS 멀티 리전/멀티 클러스터**, 트래픽 라우팅/헬스체크 기준 정립.
  * 메시징: **FCM Notification Daemon** 설계(분당 약 3,000 msg 처리), 온라인 구독(푸시 기반) 기능 확장.
  * 검색: **Elasticsearch** 기반 서버 주도 콘텐츠 검색/제공.
  * 배포/운영: GitHub Actions + EventBridge, **Slack 봇 알림**, 장애 기준/롤백/피처플래그 체계화.
  * ML/이미지: Stable Diffusion image-to-image API 도입(runpod 서버리스).
* **결과(R)**:

  * 글로벌 응답 시간 안정화 및 배포 신뢰도 향상. **누적 사용자 5,100만** 규모 운영에 필요한 표준 운영 체계 수립.

---

### 5.3 Neople – 대형 서비스 리뉴얼 & 웹게임/서버리스

* **기간/역할**: 2019.04–2023.11 Team Leader / 2009.11–2017.06 Senior Backend
* **배경(S)**: 대형 게임 IP의 웹 자산 리뉴얼, 폐쇄망 배포 체계 필요, 캐주얼 **HTML5 웹게임** 제공.
* **과제(T)**: MSA 전환, CI/CD 자동화, 폐쇄망 배포, 계정/결제 연계 안정화.
* **행동(A)**:

  * **던전앤파이터/사이퍼즈 공식 홈페이지 리뉴얼**: MSA 아키텍처, 멀티모듈 CI/CD, 계정·결제 연계, 성능·네트워크 병목 개선.
  * **폐쇄망 배포**: GitLab Runner/Nexus로 온프레미스 CI/CD 파이프라인 구축.
  * **DNF Universe**: SPA(React/MobX) 빌드.
  * **웹게임 – 비트비트 8비트**: Phaser 기반 HTML5 게임, **AWS Lambda 서버리스 랭킹 API** 설계.
* **결과(R)**:

  * 대형 릴리즈의 **배포 신뢰도/속도 향상**, 웹게임을 통한 가벼운 유입 및 브랜딩 효과.

---

### 5.4 사이드 프로젝트 (운영 안정성/자동화 역량 사례)

* **자동 블로깅 파이프라인(FDM Hub)**: 크롤링→요약→포스트 생성→PR 자동화. 실패 시 재시도·백오프, 에러 로그/슬랙 알림, 하루 단위 스케줄 운영.
* **실시간 시세 시뮬레이터(One‑Minute Trader)**: WebSocket 시세, 리스크 매니저, 시그널 처리 파이프라인, 실패 가정 설계와 스킵/재시도 로직.
* **WOD 관리(Wawo)**: MySQL 스키마(운동/블록/인스턴스) 설계, JSON WOD 피드, Admin API.

> 공통적으로 **Fail-first 가정 + 롤백/재시도/알림**을 설계하여 휴면 에러를 줄이고, 운영자가 개입하지 않아도 **자동 복구**되는 구조를 지향합니다.

---

## 6) 문제 해결 사례 (Highlight)

* **Race condition 근본 해결**: 락 테이블/이벤트 로그/아이템포턴시로 동시성 제어, 트랜잭션 경계 재설계.
* **포스트모텀 문화 정착**: 개인 비난보다 원인-대응-재발방지 액션을 표준화. Slack 알림 연동, 체크리스트/템플릿 운영.
* **검색 전환**: 클라이언트 주도에서 **서버 주도 검색/추천**으로 변경하여 응답 일관성/추적성 개선(Elasticsearch).
* **인프라 전환**: Beanstalk→EKS 멀티 리전, 배포 실패율/MTTR 감소, 관측 지표 표준화.

---

## 7) 제조/설비 연동 관점 (램프업 계획)

* **현 수준**: WebSocket 실시간 처리(개인 웹게임/실시간 시스템) 경험, **UART/Serial 통신 초급 실습** 경험.
* **램프업 로드맵**: 1) PoC(1–2주) – node-opcua/modbus-serial 등 SDK로 샘플 장비/시뮬레이터 연동 → 2) 스펙 파서/에러 재시도/버퍼링·재전송 → 3) 운영 대시보드/알림/로그/트레이싱 → 4) 성능·신뢰성 테스트(SLA/MTTR 지표).

---

## 8) 협업/리더십

* **품질 게이트**: PR 템플릿, 리뷰 규칙, 테스트 최소 기준, 릴리즈 체크리스트.
* **문서화**: ADR(Architecture Decision Record), 장애 일지/포스트모텀, 운영 Runbook.
* **지식 전파**: 온보딩 가이드, 코드 오너십, 회고(분기/릴리즈 단위).

---

## 9) 교육

* 경일대학교 제어계측공학과 (2001.03–2008.08)

---

### 부록) 링크 모음

* 비트비트 8비트(웹게임): [http://webgame.df.nexon.com/bit-bit-8bit/index.html](http://webgame.df.nexon.com/bit-bit-8bit/index.html)
* GitHub: [https://github.com/qlazzarus](https://github.com/qlazzarus)
