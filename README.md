# 🔁 Upbit Auto Trading Bot (Spring Boot 기반 자동매매 프로그램)

> **Spring Boot + Upbit Open API 기반의 자동 매매 시스템**  
> 가상 거래를 통한 백테스트 기능부터 실시간 자동 매매까지 확장 가능한 구조로 설계되었습니다.

---

## 📌 프로젝트 개요

- **목표**: 업비트 Open API를 통해 자동 매매 및 전략 검증 시스템 구현
- **백엔드**: Spring Boot (Java)
- **프론트엔드**: HTML 기반 테스트 UI → React로 확장 예정
- **DB**: 개발 단계에서는 H2, 배포 시 Firebase 고려
- **주요 기능**:
    - 가상 거래 기반 백테스트
    - 실시간 시세 조회 및 전략 분석
    - 자동 매수/매도 주문
    - 매매 로그 저장 및 시각화

---

## 🛠️ 사용 기술 스택

| 구성요소        | 기술명                          |
|----------------|------------------------------|
| 백엔드         | Spring Boot 3.5.3, WebClient |
| 프론트엔드     | HTML (→ React 예정)            |
| DB             | H2 Database (→ Firebase 예정)  |
| 테스트         | JUnit 5                      |
| 인증           | JWT (업비트 API 서명용)            |
| 빌드 도구      | Gradle                       |

---

## ⚙️ 기능 상세

### ✅ 자동매매

- 업비트 실시간 시세 조회
- 사용자 정의 전략에 따라 조건 충족 시 매수/매도 실행
- WebClient 기반 API 요청
- JWT 기반 인증 구현

### ✅ 백테스트

- 실제 매매 전, 가상 환경에서 전략 테스트
- 테스트용 주문/체결 기록 관리
- 결과 통계 리포팅 (수익률, 매매 횟수 등)
- JUnit 기반 단위 테스트 진행

### ✅ 스케줄링

- Spring `@Scheduled` 사용
- 특정 주기마다 시세 조회 및 전략 실행

### ✅ UI

- 초기: HTML + Thymeleaf (또는 간단 템플릿)
- 추후 React 기반 SPA로 리팩토링 예정

---

## 🗂️ 프로젝트 구조
UpbitAutoTrading

├── config/ # WebClient, API 키, JWT 설정

├── dto/ # 요청 및 응답 객체

├── service/ # 매매 전략 및 API 호출 로직

├── scheduler/ # 정기 실행 서비스

├── test/ # 백테스트 및 단위 테스트 코드

├── controller/ # REST API 및 테스트용 UI 연결

└── resources/

└── application.yml # 설정 파일 (API Key 등)