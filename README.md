# B-SIGHT

AI 기반 음식점 운영 소상공인 매출·비용 관리 및 경영 인사이트 서비스

## 📌 프로젝트 소개

B-SIGHT 소상공인의 매출, 비용, 손익 데이터를 통합 관리하고 AI 기반 경영 인사이트를 제공하는 서비스입니다.

매출, 비용, 인건비를 통합 관리하고 외부 식자재 시세를 자동 수집하여 손익 현황을 시각화합니다.

또한 OpenAI 기반 AI 챗봇과 경영 인사이트 기능을 통해 데이터 분석 및 의사결정을 지원하며, 직원 근태 자동 정산 기능으로 운영 효율성을 향상시킵니다.

## 주요 기능

1. 통합 매출 관리

매출 데이터를 CSV 파일로 업로드
일별 매출 추이 라인 차트 제공
채널별(매장·배달) 매출 도넛 차트 제공
요일 × 시간대 히트맵 시각화
매출·원가·인건비·고정비를 통합 분석한 매출 보고서 제공

2. 외부 시세 자동 연동

KAMIS API 기반 농수축산물 시세 조회
주요 식자재 가격 변동 추적
Naver 최저가 구매처 정보 제공

3.AI 챗봇 · 경영 인사이트

자연어 질의응답 지원
OpenAI 기반 AI 챗봇
경영 보고서 자동 생성
매출 및 비용 분석 리포트 제공

4.직원 근태 자동 정산
출퇴근 시간 관리
휴게시간 자동 반영
주휴수당 자동 계산

---

## 📂 프로젝트 구조

```bash
MIDAS/
├── frontend/              # React 기반 프론트엔드
│
└── backend/               # 백엔드
    ├── spring-server/     # Spring Boot API 서버
    └── python-crawler/    # Python 크롤링 모듈
```

---

## ⚙️ 개발 환경 (Environment)

### Frontend

| 항목                | 상세 내용                 |
| ----------------- | --------------------- |
| Framework         | React 19 + Vite 7     |
| Language          | TypeScript 5.8        |
| Styling           | Styled-Components 6.1 |
| State Management  | Jotai 2.15            |
| API Communication | Axios 1.12            |
| Package Manager   | npm                   |

### Backend

| 항목             | 버전               | 비고              |
| -------------- | ---------------- | --------------- |
| Java           | 17               | 프로젝트 소스 컴파일 대상  |
| JDK            | 22.0.2 (Temurin) | 로컬 실행 환경        |
| Spring Boot    | 3.5.6            | build.gradle 기준 |
| Gradle         | 8.14.3           | Wrapper 사용      |
| MySQL          | 8.4.6            | 기본 포트 3306      |
| Python         | 3.x              | 크롤링 모듈 실행 환경    |
| FastAPI        | 사용               | Python 서비스 연동   |
| Beautiful Soup | 사용               | 데이터 파싱          |
| Selenium       | 사용               | 동적 페이지 크롤링      |
| OpenAI API     | GPT-4o-mini      | AI 인사이트 생성      |
| Swagger        | OpenAPI 3        | API 문서화         |

---

## 💻 실행 방법

### 1. 레포지토리 복사

```bash
git clone https://github.com/YU-MIDAS-26/MIDAS.git
cd MIDAS
```

---

## 🎨 Frontend 실행

```bash
# frontend 디렉토리 이동
cd frontend

# 의존성 설치
npm install

# 개발 서버 실행
npm run dev
```

기본 개발 서버 주소:

```text
http://localhost:5173
```

---

## ⚙️ Backend 실행

### Spring Boot 서버

```bash
# backend/spring-server 이동
cd backend/spring-server

# 빌드
./gradlew clean build

# 서버 실행
./gradlew bootRun
```

API 문서:

```text
http://localhost:8080/swagger-ui.html
```

---

### Python 크롤링 모듈

```bash
# backend/python-crawler 이동
cd backend/python-crawler

# 가상환경 생성
python -m venv venv

# 가상환경 활성화

# macOS / Linux
source venv/bin/activate

# Windows
venv\Scripts\activate

# 패키지 설치
pip install -r requirements.txt

# 크롤러 실행
python scripts/run_kamis.py
```

---

## 📂 Frontend 상세 구조

### React Client

```bash
frontend/src/
├── api/              # API 통신 모듈
├── assets/           # 이미지 및 정적 리소스
├── components/       # 공통 UI 컴포넌트
├── contexts/         # 전역 상태 및 Context 관리
├── pages/            # 페이지 컴포넌트
├── style/            # 전역 스타일 및 테마
│
├── App.tsx           # 앱 진입 컴포넌트
├── Home.tsx          # 메인 페이지
├── Router.tsx        # 라우팅 설정
└── main.tsx          # 애플리케이션 엔트리 포인트
```


## 📂 Backend 상세 구조

### Spring Server

```bash
spring-server/src/main/java/com/bsight/springserver/
├── domain/
│   ├── cost/          # 고정비/변동비 관리
│   ├── finance/       # 금융 대시보드 및 AI 인사이트
│   └── sales/         # 매출 관리
│
├── global/
│   ├── ai/            # OpenAI 연동
│   ├── config/        # Swagger, Web MVC 설정
│   ├── exception/     # 전역 예외 처리
│   └── response/      # 공통 응답 포맷
│
└── common/            # 공통 유틸리티
```
