# nosol-love2

> **AI 자동화로 1인 업무를 스튜디오급 생산성으로** — 에이전트, 파이프라인, 대시보드, 비즈니스 자동화 시스템을 직접 설계·구축합니다.

---

## 🎯 What I Build

실무 현장에서 반복되는 업무를 **AI 에이전트 파이프라인**으로 치환합니다.
브라우저 자동화(Playwright/CDP), LLM 오케스트레이션(Claude), 스케줄러, 텔레그램 봇, 로컬 DB(SQLite/Postgres)로
"사람이 안 붙어도 돌아가는 시스템"을 만드는 데 집중합니다.

---

## 🤖 AI 에이전트 & 자동화 플랫폼

| 프로젝트 | 설명 | 스택 |
|---|---|---|
| **FORGE** | 자율 개발 루프. DB + 스크랩을 읽고 다음 작업을 스스로 결정 → Claude CLI 실행 → git commit 반복 | Python, Claude CLI, SQLite, Git |
| **night-agent** | 새벽 01:00~06:00 AI 웹 UI 자동 조작(Claude/ChatGPT/Gemini). 질문 수집 + 릴스 자동 제작 파이프라인 | Node.js, Playwright (CDP), Edge TTS, FFmpeg |
| **AgentOS** *(agent-dashboard)* | AI 에이전트 관리 플랫폼. 6레이어 프롬프트 컴포저, N단계 체인, 변형 생성, 해부학 분석 | React 19, FastAPI, PostgreSQL, Docker |
| **lecture-agent** | 위더스 원격교육원 자동 수강 에이전트. 공인인증서 자동 로그인, 일시정지 감지·재개 | Node.js, Playwright CDP, Telegram Bot |
| **captureReview** *(AGENT)* | 프론트엔드 QA 전 페이지 자동 캡쳐 + 리뷰 보드 → 구조화 JSON → AI 수정 프롬프트 생성 | Puppeteer, React, Node.js |

---

## 💼 비즈니스 자동화

| 프로젝트 | 설명 |
|---|---|
| **GRACE (찰나/BRIDE)** | 웨딩 사진 보정 엔드투엔드. Telegram 주문 접수 → Meitu 批处理 PyAutoGUI 자동 보정 → GDrive 납품 → Instagram 릴스 마케팅 |
| **DRIP** | 패션 중고 매물 자동 시세 조사 (KREAM/당근/번개/후루츠 병렬 비교). Pinterest 수집 → StableDiffusion 가상 피팅 → BIGFL 배대지 자동 주문 |
| **PULSE** | B2B 영업/마케팅 자동화. 리드 스캐너 + 경쟁사 스크래핑 + Claude 카피라이터 + 이메일/Discord 딜리버리 |
| **naver-place-poster** | 네이버 플레이스 자동 포스팅 (CDP 기반 에디터 주입, 스티커/표/동영상 프로빙) |
| **midjourney-client** | Midjourney Discord API 클라이언트 + 프롬프트 빌더 |

---

## 📈 금융·투자 리서치 시스템

| 프로젝트 | 설명 |
|---|---|
| **SolSet 자동매매** | S&P 500 전종목 히스토리컬 데이터에서 통계 규칙 자동 발견(5 엔진·124 규칙) → 실시간 스캐너 → FastAPI+SSE 대시보드 |
| **stock_company** | DART 사업보고서 자동 스크래핑 + Claude 재무 추출 → 한국 조선 6사 비교 분석 |
| **us_defense** | SEC EDGAR XBRL 자동 수집 → 프롬프트 자동 결합 → Claude 웹 자동 질의 → 방위/드론/eVTOL 11사 분석 |
| **ROI:ME** | 커리어 재무 엔진. 모든 업무의 기대이익·연봉협상 근거·정년까지의 총소득을 수치 설계 |

---

## 🛠 생산성 도구

| 프로젝트 | 설명 |
|---|---|
| **PMT** *(pmtsystem)* | 프로젝트/마일스톤/태스크/스크랩/AI 질문 올인원 대시보드. 13 테이블, 25+ API, Cloudflare Tunnel 외부 접속 |
| **RTA** | Flutter 루틴 타이머 앱. 텍스트 한 줄 일괄 입력 + TTS 음성 안내 + 40px 고밀도 대시보드 |
| **dailyWorkAutoList** | 매일 아침 업무 수집 + 매주 금요일 AI 주간보고서 자동 생성. CLI 한 줄로 재사용 가능한 프로젝트 템플릿 생성기 포함 |
| **telegram-hub** | 텔레그램 통합 허브 — 여러 봇의 알림/원격 제어 일원화 |
| **TOEIC990** | 토익 만점화 SRS 학습 시스템. PDF→OCR→질문 분해→유형/함정 태깅, SM-2 변형 알고리즘 |

---

## 🎨 웹 & 포트폴리오

- **safed-astro** — 세이프디 공식 웹 (Astro)
- **portfolio-auto-system (HSN)** — 풀스택 크리에이터 포트폴리오
- **safed_renewal** — 세이프디 리뉴얼 프로젝트

---

## ⚙️ 기술 스택

**Languages** Python 3.11+ · TypeScript · JavaScript · Dart
**Frontend** React 19 · Vite · Tailwind · Astro · Flutter · Electron
**Backend** FastAPI · Express · Node.js · SQLAlchemy (async) · better-sqlite3
**AI** Anthropic Claude (API + 웹 자동화) · Edge Neural TTS · Tesseract OCR · Stable Diffusion
**자동화** Playwright (CDP) · Puppeteer · PyAutoGUI · FFmpeg
**데이터** PostgreSQL · SQLite (WAL) · Redis
**인프라** Docker Compose · PM2 · Windows Task Scheduler · Cloudflare Tunnel
**메시징** Telegram Bot API · Slack · Discord · Instagrapi · YouTube Data API

---

## 🧭 설계 원칙

- **AI 호출은 한 경로로만** — 프로젝트 전체에서 `night-agent` 경유 (직접 API 호출 금지)
- **ADHD 워크플로우** — 한 번에 하나의 태스크, 마일스톤 게이트로 완료 확인 후 다음
- **로컬 우선** — SQLite + 로컬 자동화 → 필요해지면 서버/클라우드로 승격
- **재사용 가능한 템플릿화** — 자동화 아키텍처 자체를 템플릿으로 떠서 새 업무에 바로 얹기

---

<sub>📬 각 프로젝트는 개별 레포로 공개 예정입니다.</sub>
