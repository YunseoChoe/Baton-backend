<br>
<div align="center">
  <img width="256" height="256" alt="Baton-logo" src="https://github.com/user-attachments/assets/6847e6c1-a47c-4d15-af1d-9c5630b5354a" />
  <h3 align="center">Baton 🤝</h3>
  <p align="center">
    크레딧 · 에스크로 기반 1:1 안전 재능 교환 플랫폼<br>
  </p>
</div>
<br>


<details open>

  <summary><strong>📖 목차</strong></summary>

1. [🔍 서비스 소개](#-서비스-소개)
2. [📄 API 명세서](#-api-명세서)
3. [💡 기술 스택](#-기술-스택)
4. [🗂️ 데이터베이스](#️-데이터베이스)
5. [💻 시스템 아키텍처](#-시스템-아키텍처)
6. [💡 핵심 설계 의사결정](#-핵심-설계-의사결정)
7. [🤝 깃 컨벤션](#-깃-컨벤션)
8. [📂 프로젝트 구조](#-프로젝트-구조)
9. [🎬 실행하기](#-실행하기)
10. [👨‍👩‍👧‍👧 역할 분담](#-역할-분담)
</details>

<br>

## 🔍 서비스 소개

### 배경
 
기존 재능 교환 플랫폼은 높은 금전적 장벽이 있거나, 서비스의 고질적인 문제인 '거래 사기'와 '안전 장치 부재' 문제가 있었습니다. <br>
이를 해결하기 위해 **Baton**은 가상 크레딧(Credit)과 에스크로(Escrow) 결제 모델을 결합하여, 금전적 부담 없이 누구나 100% 안전하게 재능을 교환할 수 있는 신뢰 기반의 플랫폼을 구축했습니다.

### 주요 기능
- **재능 등록 및 매칭**: 카테고리 기반 재능 검색 및 단방향·양방향 매칭 시스템 지원
- **에스크로(Escrow) 기반 안전 거래**: 거래 완료 전까지 결제 대금을 보관하여 사기 방지 및 신뢰성 확보
- **크레딧(Credit) 시스템**: 플랫폼 내 재화(크레딧)를 활용한 결제 및 정산
- **DB 락을 활용한 동시성 제어**: 쿼리 기반 원자적 업데이트를 통해 다중 결제 요청 시 데이터 정합성 보장
- **실시간 채팅(STOMP)**: JWT 기반 보안 인터셉터가 적용된 안전한 1:1 채팅 지원
- **AWS S3 Presigned URL**: 클라이언트 직접 업로드를 통한 서버 부하 절감 및 대용량 파일 관리
- **Sentry 기반 실시간 로깅**: 예외 발생 시 실시간 에러 모니터링 및 추적
- **JaCoCo 테스트 커버리지 관리**: 안정적인 서비스 운영을 위한 코드 품질 검증

<br>

## 📄 API 명세서

> Swagger UI 기반 API 문서 제공

- Trade
<img width="1225" height="436" alt="8-trade" src="https://github.com/user-attachments/assets/3ceebb2c-8425-4450-bbb4-ca64d78ebea1" />

- Talent
<img width="1225" height="388" alt="4-talent" src="https://github.com/user-attachments/assets/e2e2eb3b-b204-4190-8a91-0bc563d89ae1" />

- Category & Talent Attachment
<img width="1225" height="357" alt="3-talent" src="https://github.com/user-attachments/assets/ded4664e-3411-42b1-98d8-cba9b36079c3" />

- Matching & Chat
<img width="1225" height="306" alt="5-match chat" src="https://github.com/user-attachments/assets/4a755ff8-6473-4e9a-8ccb-f07bfa51b0d9" />

- ChatRoom
<img width="1225" height="199" alt="2-chat" src="https://github.com/user-attachments/assets/ffb2821b-2b1c-4a00-8075-9edf862f76f1" />

- Auth
<img width="1225" height="389" alt="6-auth" src="https://github.com/user-attachments/assets/2b541b75-f9c3-45ea-8583-3d9c2f1559d7" />

- User & Profile & Matching
<img width="1225" height="557" alt="9-user profile" src="https://github.com/user-attachments/assets/5742b0cf-3455-4c37-a71e-9f228e490465" />

- Admin
<img width="1225" height="481" alt="1-admin(2)" src="https://github.com/user-attachments/assets/cdc9068c-4c41-469a-903d-dd4b5dfcca16" />

- Admin Dashboard & Credit
<img width="1225" height="523" alt="baton-api-8" src="https://github.com/user-attachments/assets/1812b9d1-7c8b-440c-a75d-8a04b3fcce0c" />
<br>

<br>

## 💡 기술 스택

Frontend | Backend | Security | Database | Deployment | Other
|:------:|:------:|:------:|:------:|:------:|:------:|
|<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white"/>|<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/><br><img src="https://img.shields.io/badge/SpringBoot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/><br><img src="https://img.shields.io/badge/JPA-59666C?style=flat-square&logo=hibernate&logoColor=white"/>|<img src="https://img.shields.io/badge/SpringSecurity-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/><br><img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white"/><br><img src="https://img.shields.io/badge/OAuth2-3423A6?style=flat-square&logo=auth0&logoColor=white"/>|<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/><br>|<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>|<img src="https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white"/><br><img src="https://img.shields.io/badge/Swagger-85EA2E?style=flat-square&logo=swagger&logoColor=black"/><br><img src="https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white"/>

```text
- Frontend : Next.js
- Backend : Spring Boot, Kotlin, JPA
- Security : Spring Security, JWT
- Database : MySQL
- Infra : AWS EC2, Docker, GitHub Actions
- Storage : AWS S3
- Test : JUnit5, JaCoCo
```

<br>

## 🗂️ 데이터베이스
<img width="992" height="749" alt="Team03-erd" src="https://github.com/user-attachments/assets/a56f2fb6-035e-402e-8ee5-a9aaf8bf0ca7" />
<br>

<br>
<br>

## 💻 시스템 아키텍처
<img width="1920" height="1080" alt="Baton_시스템아키텍처" src="https://github.com/user-attachments/assets/f50fbdff-e511-431c-af5c-88a5c2583b76" />
<br>

<br>
<br>

## 💡 핵심 설계 의사결정

### 1. 크레딧 결제 동시성 제어 (원자적 업데이트)
- **배경**: 사용자가 동시에 여러 거래를 수행할 경우 경쟁 상태(Race Condition)로 인해 잔액이 초과 결제되거나 음수가 되는 문제가 발생할 수 있습니다.
- **해결책**: 별도의 분산 락을 도입하여 복잡도를 높이는 대신, JPA `@Modifying`과 `@Query`를 활용해 DB 레벨에서 `UPDATE ... WHERE balance >= amount` 형태의 **원자적 업데이트(Atomic Update)**를 적용했습니다.
- **검증 및 성과**: 데이터 정합성을 보장하면서도 기존 대비 처리량(TPS) 약 2.6배 향상, 평균 응답 시간 83.3% 감소를 달성했습니다.
  <br>
  | 성능 평가 지표 | 비관적 락 | 원자적 업데이트 | 개선율 |
  | --- | --- | --- | --- |
  | 총 처리 건수 | 32,612건 | 85,166건 | 2.61배 처리량 증가 |
  | 평균 응답 속도 | 36ms | 6ms | 83.3% 단축 |
  | 최대 응답 지연 | 958.32ms | 615.69ms | 약 35.7% 개선 |
  | 테스트 에러율 | 0% | 0% | - |

---

### 2. 카테고리 조회 시 불필요한 DB 접근 제거 (Caffeine 로컬 캐싱)
- **배경**: 카테고리 목록은 데이터 변경 빈도가 매우 낮음에도 불구하고, 사용자가 여러 화면을 탐색할 때마다 매번 DB 조회가 반복적으로 발생했습니다.
- **해결책**: 단일 서버 환경임을 고려해 인프라 추가 비용이 발생하는 분산 캐시(Redis 등) 대신, Spring Boot에서 권장하고 설정이 간단한 메모리 기반의 **Caffeine 로컬 캐시**(`@Cacheable`)를 도입했습니다.
- **검증 및 효과**: k6 부하 테스트 및 SQL 로그를 통해 검증한 결과, 동일 요청(5회) 기준 DB 조회가 5회에서 1회로 감소(80% 감소)하여 불필요한 반복 DB 접근을 효과적으로 제거했습니다.

---

### 3. Cursor 기반 No-Offset Pagination을 활용한 조회 성능 최적화
- **배경**: 무한 스크롤이 적용된 재능 목록 등에서 기존 Offset 페이징(`LIMIT 20 OFFSET N`)을 사용할 경우, 뒤 페이지로 갈수록 읽고 버리는 데이터가 많아져(Deep Paging) 탐색 비용이 선형적으로 증가하는 문제가 있었습니다.
- **해결책**: 마지막으로 조회한 데이터의 식별자를 기준으로 그 이후의 데이터만 조회하는 **Cursor 기반 페이징**(`WHERE id < :cursor`)을 채택했습니다. 무한 스크롤 환경이므로 페이지 점프 기능의 부재는 문제가 되지 않았습니다.
- **검증 및 효과**: 10만 건 더미 데이터 생성 후 9만 번째 페이지 접근 시 실제 스캔 row 수를 `EXPLAIN ANALYZE`로 비교한 결과, Offset 방식(스캔 90,020건, ~29ms) 대비 Cursor 방식(스캔 20건, ~0.18ms)으로 **PK Range Scan**을 수행하여 조회 성능을 획기적으로 개선했습니다.
  | 성능 평가 지표 | Offset | Cursor |
  | --- | --- | --- | 
  | 스캔 row 수 | 90,020 | 20 |
  | 실행 시간 | ~29ms | ~0.18ms |
  | 접근 방식 | PK 역방향 풀스캔 후 버림 | PK range scan |
  

---

### 4. 서버 네트워크 병목 해소를 위한 AWS S3 Presigned URL 도입
- **배경**: 클라이언트가 서버를 거쳐 대용량 파일을 업로드하면, 서버의 메모리 사용량과 네트워크 대역폭 점유율이 급증하여 병목이 발생합니다.
- **해결책**: 백엔드에서는 권한이 부여된 임시 URL(Presigned URL)만 발급하고, 클라이언트가 직접 S3로 파일을 업로드 및 다운로드하도록 구조를 개편했습니다.
- **기대 효과**: 서버 네트워크 부하 및 메모리 사용량을 획기적으로 줄이고, 파일 업로드/다운로드 속도를 개선했습니다.

---

### 5. 양방향 거래 구조 모델링과 채팅방 기준 통합
- **배경**: SWAP(교환) 수락 시 실제로는 2건의 Trade(거래)가 생성되지만, 사용자는 이를 하나의 교환 거래로 인식해야 합니다. 기존처럼 `trade_id`만을 기준으로 하면 1개의 교환임에도 채팅방이 2개로 분리되는 문제가 발생했습니다.
- **해결책**: `TradeGroup` 엔티티를 새롭게 도입하여 양방향 거래를 하나로 묶었습니다. 일반 구매(PURCHASE)는 `trade_id`, 교환(SWAP)은 `trade_group_id`를 기준으로 단일 채팅방이 생성되도록 변경했습니다. 또한, `PESSIMISTIC_WRITE` 락과 `REQUESTED` 상태 검증을 통해 동시 다발적 수락 요청에 의한 중복 거래를 방어했습니다.
- **기대 효과**: 사용자 경험(UX)과 도메인 구조를 일치시켰으며, 하나의 수락 트랜잭션 내에서 거래, 에스크로 보관, 채팅방 생성을 안전하고 매끄럽게 처리할 수 있게 되었습니다.


<br>

## 🤝 깃 컨벤션

### Branch 전략

GitHub Flow 기반 운영

| 브랜치명 | 역할 |
| --- | --- |
| main | 운영 브랜치 |
| dev | 개발 통합 브랜치 |
| feature/* | 기능 개발 |

## 커밋 전략

```text
type: 작업내용
```

예시

```text
feat: 크레딧 결제 API 추가
```

| 타입 | 의미 |
| --- | --- |
| feat | 기능 추가 |
| fix | 버그 수정 |
| refactor | 리팩토링 |
| test | 테스트 |
| docs | 문서 수정 |
| chore | 설정 변경 |

<br>

## 📂 프로젝트 구조

```text
backend
├── src
│   ├── main
│   │   ├── java/com/back/baton
│   │   │   ├── domain
│   │   │   │   ├── admin
│   │   │   │   ├── category
│   │   │   │   ├── chat
│   │   │   │   ├── credit
│   │   │   │   ├── escrow
│   │   │   │   ├── matching
│   │   │   │   ├── profile
│   │   │   │   ├── talent
│   │   │   │   ├── trade
│   │   │   │   └── user
│   │   │   └── global
│   │   │       ├── config
│   │   │       ├── exception
│   │   │       ├── filter
│   │   │       ├── response
│   │   │       ├── s3
│   │   │       ├── security
│   │   │       └── util
│   │   └── resources
│   └── test
├── docs
├── load-tests
├── gradle
├── Dockerfile
├── compose.yaml
└── build.gradle.kts
```


<br>

## 🎬 실행하기

### 요구 사항

- Java 21
- Docker
- Docker Compose

### 애플리케이션 실행

```bash
./gradlew bootRun
```

Windows

```powershell
.\gradlew.bat bootRun
```

### API 문서

- Swagger UI : http://localhost:8080/swagger-ui/index.html
- OpenAPI : http://localhost:8080/v3/api-docs

### 배포 환경

- 서비스 : http://baton.io.kr
- Backend : http://54.116.23.255
- Swagger : http://54.116.23.255/swagger-ui/index.html

<br>

## 👨‍👩‍👧‍👧 역할 분담

| 이름 | 역할 | 도메인 |
| --- | --- | --- |
| 남진우 | 팀장(PO) · 아키텍트형 역할 | 관리자 모니터링 |
| 박재현 | 아키텍트형 역할 · API 구현 | 재능 · 카테고리 |
| 이유진 | API 구현 · AWS 담당 | 회원 ·  프로필 |
| 이인희 | API 구현 · 고급기능 & 성능 개선 · 프론트엔드| 매칭 ·  채팅 |
| 최윤서 | API 구현 · 고급기능 & 성능 개선 | 크레딧 · 에스크로 · 거래 |
