# Full-stack / AI Automation Engineer

LLM 기반 워크플로우 설계, 브라우저·데스크탑 자동화, 데이터 파이프라인, 풀스택 웹/모바일 애플리케이션을 end-to-end로 구현합니다.

---

## Core Competencies

| 영역 | 기술 |
|---|---|
| **Languages** | Python, TypeScript, JavaScript (Node.js), Dart |
| **Frontend** | React, TypeScript, Vite, Tailwind CSS, Astro, Flutter, Electron |
| **Backend** | FastAPI, Express.js, SQLAlchemy (async), Alembic |
| **Databases** | PostgreSQL, SQLite (WAL), Redis |
| **LLM / AI** | LLM API 연동, Prompt Engineering, SSE 스트리밍, Tool Use |
| **Automation** | Playwright (CDP), Puppeteer, 데스크탑 GUI 자동화, FFmpeg |
| **Data** | 공개 API 스크래핑, pandas, OCR, PDF 파싱 |
| **Infra / DevOps** | Docker Compose, 프로세스 매니저(PM2), Alembic 마이그레이션, 터널링, JWT 인증 |
| **Integrations** | 메시징 봇(Bot API), OAuth2, 클라우드 스토리지 API |

---

## Representative Work

### 1. LLM Orchestration Platform *(Full-stack)*

LLM 기반 워크플로우를 시각적으로 설계·실행·개선하는 풀스택 애플리케이션.

- **Frontend**: React + TypeScript + Vite, Zustand + TanStack Query, Tailwind
- **Backend**: FastAPI + SQLAlchemy(async) + Alembic, PostgreSQL
- **Infra**: JWT 인증, Docker Compose 멀티 서비스
- **Highlights**:
  - 다중 레이어 프롬프트 편집기 + 완성도 점수 알고리즘
  - N-step 체인 실행 엔진 (이전 단계 출력 → 다음 단계 컨텍스트 자동 주입)
  - 프롬프트 버전 히스토리 & Diff
  - SSE 스트리밍으로 실행 진행률 실시간 표시
  - Cron 기반 스케줄링 + 실패 시 지수 백오프 재시도

### 2. Project / Task 통합 대시보드 *(Full-stack SPA)*

개인 생산성용 데이터 통합 대시보드.

- Node.js + Express + SQLite(better-sqlite3, WAL)
- 11개 라우트 모듈 · 13 테이블 · 25+ API · Vanilla JS SPA
- 모바일 반응형 UI, 이미지 업로드(multer), 터널링으로 외부 접속 노출
- 엔티티 간 다중 조인 스키마 설계 및 인덱스 최적화

### 3. Autonomous Development Loop

데이터베이스에서 작업 큐를 읽어 다음 태스크를 자동 판단하고, LLM CLI로 실행 → 버전 관리 커밋 → 반복하는 자율 실행 루프.

- LLM 출력 형식을 스키마로 강제해 파싱 실패율 최소화
- 프로젝트별 작업 디렉토리 격리, 사이클 단위 JSONL 로그
- 안전 가드(최대 사이클 수·실행 타임아웃·작업 범위 제약)

### 4. Multi-channel Service Automation

수동 업무 전 과정을 메시징 → 처리 → 산출물 배포까지 자동화한 end-to-end 시스템.

- 메시징 봇으로 24/7 요청 접수
- 데스크탑 애플리케이션 GUI 자동화 기반 일괄 처리
- 클라우드 스토리지 API로 폴더 생성·업로드·공유 링크 자동 발급
- FFmpeg 기반 미디어 후처리 파이프라인 + 예약 배포

### 5. Multi-source Data Aggregation Pipeline

여러 소스에서 데이터를 병렬 수집·정규화·판정하는 파이프라인.

- 다중 출처 병렬 스크래핑 (Playwright/HTTP)
- 비전 모델 + OCR 기반 이미지 속성 추출
- 이미지 처리 파이프라인 (배경 제거·합성·리사이즈)
- 규칙 + LLM 하이브리드 판정 엔진

### 6. Frontend QA Automation CLI

Puppeteer 기반 프론트엔드 QA 자동화 CLI 툴.

- 전 페이지 자동 크롤링 + 뷰포트별(desktop/tablet/mobile) 스크린샷
- 리뷰 UI 자동 생성, 스크린샷 섹션 자동 감지, 코멘트·우선순위·카테고리 분류
- 구조화 JSON export → LLM 수정 프롬프트로 직접 투입 가능
- 시스템 PATH 등록, 단일 명령어 실행

### 7. Cross-platform Mobile Routine App

Flutter 크로스플랫폼 모바일 앱.

- Flutter + Cloud Firestore + Riverpod
- 텍스트 DSL 기반 일괄 등록(1줄 = 1항목) → 입력 비용 최소화
- 고밀도 대시보드(고정 행 높이, 그룹 자동 분류)
- 한국어 TTS 음성 가이드

### 8. Business Automation Framework

업무 자동 수집 + AI 리포트 생성 프레임워크 + **프로젝트 템플릿 생성기**.

- OS 스케줄러 기반 정기 실행(수집/리포트)
- 대화형 CLI로 동일 아키텍처 기반의 새 자동화 프로젝트를 즉시 스캐폴딩(메타 템플릿화)

---

## Engineering Principles

- **Contract-first LLM 호출** — 출력 형식을 스키마로 강제해 자유도를 제한, 파싱 실패율 최소화
- **로컬 우선 → 승격** — SQLite + 로컬 자동화로 시작해서 필요해지면 PostgreSQL/Docker로 승격
- **단일 경로 원칙** — AI 호출·파일 경로·로깅 단일화로 중복 구현 제거 및 유지보수 비용 통제
- **메타 템플릿화** — 검증된 자동화 아키텍처를 템플릿으로 떠서 다른 도메인에 재사용
- **최소 단위 배포** — 한 번에 하나의 태스크, 마일스톤 게이트로 완료 확인 후 다음 단계 진행
