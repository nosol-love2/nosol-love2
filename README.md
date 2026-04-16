# nosol-love2

**Full-stack AI Automation Engineer** — LLM 오케스트레이션, 브라우저 자동화, 데이터 파이프라인, 풀스택 대시보드를 end-to-end로 설계·구현합니다.

> 실제 비즈니스 문제(보정 스튜디오 운영, 주식 시그널 탐색, 중고 거래 시세 비교, 기업 재무 리서치)를 AI + 자동화로 해결한 시스템을 직접 구축해 왔습니다.

---

## 📌 Core Competencies

| 영역 | 기술 |
|---|---|
| **Languages** | Python 3.11+, TypeScript, JavaScript (Node.js), Dart |
| **Frontend** | React 19, Vite, TypeScript, Tailwind CSS 4, Astro, Flutter, Electron |
| **Backend** | FastAPI, Express.js, SQLAlchemy (async), Alembic, better-sqlite3 |
| **Databases** | PostgreSQL 15, SQLite (WAL mode), Redis |
| **AI / LLM** | Anthropic Claude API, Prompt Engineering, SSE Streaming, Tool Use |
| **Automation** | Playwright (CDP), Puppeteer, PyAutoGUI, FFmpeg |
| **Data** | SEC EDGAR XBRL, DART API, pandas, pdfplumber, Tesseract OCR |
| **Infra / DevOps** | Docker Compose, PM2, Alembic Migrations, Cloudflare Tunnel, JWT Auth |
| **Messaging** | Telegram Bot API, Slack Webhooks, OAuth2 (Google / YouTube) |

---

## 🏗 Key Projects

### 1. AgentOS — AI 에이전트 관리 플랫폼 *(Full-stack)*

LLM 기반 워크플로우를 시각적으로 설계·실행·개선하는 풀스택 플랫폼.

- **Frontend**: React 19 + TypeScript + Vite, Zustand + TanStack Query, Tailwind CSS 4
- **Backend**: FastAPI + SQLAlchemy (async) + Alembic, PostgreSQL 15
- **Auth / Infra**: JWT (python-jose, HS256), Docker Compose (3 services)
- **AI**: Anthropic SDK, SSE 스트리밍으로 N단계 프롬프트 체인 실시간 실행 표시
- **핵심 기능**:
  - 6-레이어 프롬프트 컴포저(Role/Context/Task/Format/Constraint/Example)와 완성도 점수 알고리즘
  - 에이전트 N단계 체인 실행 엔진(이전 단계 output → 다음 단계 context 자동 주입)
  - 프롬프트 버전 히스토리 & Diff, A/B/C형 변형 자동 생성
  - APScheduler 기반 Cron 실행 + 실패 시 지수 백오프 재시도
- **스키마 설계**: 8개 핵심 테이블, UUID PK, soft delete, JSONB 활용

### 2. SolSet — S&P 500 규칙 발견·자동매매 시스템

503 종목 히스토리컬 데이터에서 통계 기반 트레이딩 규칙을 자동 발견하고 실시간 스캐너로 매매하는 end-to-end 시스템.

- **Rule Discovery Engine**: 5개 엔진(세션 17개·장중 81개·주간 계절성 19개·지정학 7개·캘린더)으로 124+ 규칙 자동 생성. `hit_rate ≥ 55%`, `sample ≥ 30` 필터링.
- **Realtime Scanner**: S&P 500 × 60초 스캔, 50종목 chunk 병렬 다운로드, score 합산 → `score ≥ 4.0` BUY / 손절 `-2%` / 계획 청산시각 SELL
- **Position Manager**: 최대 5 포지션 · 1회 $50 · 5분 체크포인트 저장
- **Dashboard**: FastAPI + SSE(5초 주기 push), 규칙 테이블 · 실시간 스캔 결과 · 포지션 · PnL · 런타임 설정 변경(파일 영구 저장)

### 3. PMT — Project Management Tool *(Full-stack SPA)*

프로젝트·마일스톤·태스크·스크랩·AI 질문을 통합 관리하는 1인용 생산성 대시보드.

- **Stack**: Node.js + Express + SQLite (better-sqlite3, WAL mode)
- **Architecture**: 11개 라우트 모듈, 13개 테이블, 25+ API, Vanilla JS SPA
- **Features**:
  - iPhone 14 Pro 최적화 반응형 SPA
  - multer 기반 이미지 업로드
  - Cloudflare Tunnel로 외부 접속 즉시 노출
  - projects ↔ milestones ↔ tasks ↔ scraps ↔ ai-questions 5-way join 스키마

### 4. FORGE — Autonomous Development Loop

DB + 스크랩 데이터를 읽고 **다음 작업을 스스로 결정**해 Claude CLI로 실행 → git commit → 반복하는 자율 개발 루프.

- **Loop**: `db_reader.py` → `prompt_planner.py` → `claude_runner.py` → `git_committer.py` → `logs/cycles.jsonl`
- **Planner**: 프롬프트 출력 형식을 강제해서 LLM의 자유도를 제한 (프로젝트/경로/현재상태/작업/완료조건/제약 6개 슬롯)
- **Safety**: MAX_CYCLES=100, 프로젝트 cwd 기반 git commit 분리, JSONL 사이클 로그

### 5. GRACE — Wedding Photo Retouch Automation *(B2C Service Automation)*

웨딩 사진 보정 스튜디오의 수동 업무를 end-to-end 자동화.

- **Order Pipeline**: Telegram Bot 24/7 주문 접수 → 고객별 폴더 자동 생성
- **Retouch Engine**: PyAutoGUI로 Meitu 批处理 제어, 프리셋 기반 일괄 보정
- **Delivery**: Google Drive API로 폴더 생성·업로드·공유 링크 자동 전송
- **Marketing**: FFmpeg 기반 Before/After 릴스 자동 생성 + Instagrapi 예약 업로드
- **Business Impact**: 납기 1주일 → 1-2일로 단축, 월 운영비 ~₩200 (Meitu VIP)

### 6. DRIP — Fashion Reselling Intelligence Pipeline

패션 중고 시세 비교 및 자동 매입/리스팅 파이프라인.

- **Multi-platform Price Discovery**: KREAM · 당근마켓 · 번개장터 · 후루츠패밀리 병렬 시세 조사
- **AI Vision**: Claude Vision + Google Lens + OCR로 브랜드/가격/컨디션 식별
- **Virtual Try-On**: Stable Diffusion 기반 가상 피팅 합성
- **Listing Builder**: 배경 제거(rembg) + Pillow 합성 + 감성 카피 자동 생성
- **Decision Engine**: 시세 분석 + 리스크 판단 → BUY/WATCH/SKIP 자동 판정

### 7. US Defense Sector Analyzer — SEC EDGAR 재무 리서치 자동화

미국 방위/드론/eVTOL 상장사 11개를 대상으로 재무 데이터 수집 → AI 분석을 완전 자동화.

- **Data Pipeline**: SEC EDGAR XBRL API 스크래핑 → 대시보드 포맷 JSON 변환
- **Market Data**: Playwright로 Yahoo Finance 실시간 주가 수집
- **AI Analysis**: 맞춤 전문 프롬프트 + 재무 데이터 자동 결합 → Claude 분석 결과 자동 저장
- **Targets**: LMT, RTX, NOC, GD, LHX, BA, AVAV, KTOS, JOBY, ACHR, ONDS

### 8. 한국 조선업 재무 분석 시스템 *(stock_company)*

DART 사업보고서 자동 수집 → LLM 재무 데이터 추출 → 비교 대시보드.

- **Stack**: Playwright CDP + Anthropic API + 로컬 HTTP 서버 (HTML ↔ 데이터 브릿지)
- **Coverage**: HD한국조선해양, HD현대중공업, 삼성중공업, 한화오션, HD현대미포, HD현대삼호
- **Pipeline**: DART 스크래핑 → PDF JSON 저장 → AI 추출 → HTML 대시보드 렌더

### 9. captureReview — Frontend QA Capture Tool

Puppeteer 기반 프론트엔드 QA 자동화 CLI.

- **Features**: 전 페이지 자동 크롤링 + 뷰포트별(desktop/tablet/mobile) 스크린샷
- **Review Board**: React 리뷰 UI 자동 생성, 스크린샷 섹션 자동 감지, 코멘트·우선순위·카테고리 분류
- **AI Handoff**: Export JSON → 페이지 경로/뷰포트/섹션/y좌표 구조화 → AI에 직접 전달 가능한 수정 요청 포맷
- **Distribution**: 시스템 PATH 등록, 어디서든 `cr` 한 줄로 실행

### 10. RTA — Routine Timer App *(Mobile)*

Flutter 크로스플랫폼 루틴 타이머 앱.

- **Stack**: Flutter + Cloud Firestore + Riverpod
- **UX 실험**: 텍스트 한 줄 일괄 입력 문법(`양치/2`) → 20개 작업을 10초에 등록
- **Density**: 행 높이 40px 고정 → 한 화면에 16+ 루틴, 그룹별 자동 분류
- **Voice**: 한국어 TTS로 카운트다운 + 잔여 시간 음성 안내(50%/1분/15초)

### 11. dailyWorkAutoList — Business Automation Framework

업무 자동 수집 + AI 주간보고서 생성 + **재사용 가능한 프로젝트 템플릿 생성기**.

- **Scheduler**: Windows Task Scheduler 기반 매일 아침 수집 / 매주 금요일 보고서 생성
- **Meta-tool**: `create_project.py` 대화형 CLI로 동일 아키텍처의 새 자동화 프로젝트를 즉시 스캐폴딩

---

## 🧭 Engineering Principles

- **Contract-first LLM 호출** — 출력 형식을 스키마로 강제해 LLM의 자유도를 제한, 파싱 실패율 최소화
- **로컬 우선, 승격 전략** — SQLite + 로컬 자동화로 시작 → 필요해지면 PostgreSQL/Docker로 승격
- **단일 경로 원칙** — AI 호출/파일 경로/로깅 단일화. 중복 구현 제거로 유지보수 비용 통제
- **ADHD 워크플로우** — 한 번에 하나의 태스크, 마일스톤 게이트로 완료 확인 후 다음 단계. 코드/문서 모두 최소 단위
- **메타 템플릿화** — 자동화 시스템을 구축한 뒤 아키텍처 자체를 템플릿으로 떠서 다른 도메인에 즉시 재사용

---

## 📬 Contact

개별 프로젝트 코드/데모는 요청 시 비공개 레포 액세스로 공유 가능합니다.
