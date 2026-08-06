Suyong Park — Developer Portfolio

<div align="center">

Python Backend · FastAPI · Data Quality / ETL · AI Workflow

Python과 FastAPI를 중심으로 데이터가 들어오고, 검증되고, 저장되고, 처리되고, 배포되는 전체 흐름을 직접 구현하고 있습니다.<br/>기능 개수보다 문제 원인 파악 → 구조 개선 → 테스트 → 배포 검증 → 문서화까지 끝내는 개발을 지향합니다.



</div>

About Me

주력 직무: Python · FastAPI 백엔드 개발

관심 분야: AI 서비스 백엔드, 데이터 품질, ETL, 데이터 플랫폼, 패션·이커머스 백엔드

개발 방식: 작은 기능부터 구현하고 테스트로 검증한 뒤, CI와 문서까지 함께 관리합니다.

문제 해결 경험: 중복 처리, 비동기 작업, 데이터 표준화, DB 마이그레이션, 트랜잭션, Audit, Rollback, Docker·AWS 실행 검증을 경험했습니다.

협업 경험: 기업 연계 4인 팀 프로젝트에서 팀 리드와 MCP 서버 개발을 담당했습니다.

Tech Stack

분류

기술

Core Backend

Python, FastAPI, PostgreSQL, SQLAlchemy, Alembic

Data / ETL

pandas, SQL, CSV Processing, Data Validation, Supplier Profile Mapping

Async / Queue

Redis, Celery

Test / Quality

pytest, Unit Test, Integration Test, Browser E2E, GitHub Actions

Infra / Deploy

Docker, AWS EC2, AWS RDS, Railway, Streamlit

AI / Workflow

LangGraph, MCP, FastMCP, Local LLM

Additional Experience

Java, C, C#, HTML/CSS, OpenCV, Linux, Git/GitHub

Core Backend은 현재 취업 준비의 중심 기술이며, Additional Experience는 수업·프로젝트를 통해 사용한 기술입니다.

Featured Projects

1. CatalogGuard Lite — Fashion Catalog Data Quality Backend

서로 다른 공급사 상품 CSV를 표준화하고 자동 검수한 뒤,안전하게 카탈로그에 반영하고 변경 이력과 Rollback까지 관리하는 데이터 품질 백엔드 프로젝트

프로젝트 목적

패션·이커머스 상품 데이터에는 공급사마다 다른 컬럼명, 누락값, 중복 상품, 비표준 색상·사이즈, 가격 오류 등 다양한 문제가 발생할 수 있습니다.

CatalogGuard Lite는 이러한 데이터를 다음 흐름으로 처리하도록 만든 개인 프로젝트입니다.

Supplier CSV
    ↓
File Validation
    ↓
Profile-based ETL
    ↓
Catalog Data Inspection
    ↓
PostgreSQL Persistence
    ↓
ETL History
    ↓
Promotion Preview
    ↓
Approval / Promotion
    ↓
History / Audit
    ↓
Rollback Preview / Rollback

핵심 기능

CSV 파일 형식 및 입력값 검증

필수값 누락, 데이터 형식 오류 탐지

상품 ID 중복 및 완전 중복 탐지

가격 오류·이상치 및 sale_price 검수

상품명·카테고리 불일치 탐지

금지어·위험 표현·개인정보 의심 정보 탐지

패션 색상·사이즈 표준화

동일 색상·사이즈 옵션 조합 중복 탐지

상품 그룹 내 카테고리 불일치 탐지

검수 결과 PostgreSQL 저장·검색·조회

Redis + Celery 기반 비동기 검수

공급사 JSON Profile 기반 ETL

ETL 실행 결과 및 오류 이력 조회

Promotion Preview → 사용자 승인 → 실제 카탈로그 반영

Promotion History 및 Audit 조회

Rollback Preview, 충돌 확인, Transaction 기반 Rollback

Streamlit 관리 UI

Docker 및 AWS EC2·RDS 실행 검증

GitHub Actions 기반 자동 테스트·Runtime Smoke Test

주요 문제 해결

문제

해결

같은 CSV를 다시 올릴 때 전체 검수를 반복함

file_sha256 + inspection_version으로 기존 결과를 먼저 조회해 불필요한 재검수 방지

공급사마다 CSV 컬럼 구조가 다름

JSON Profile 기반 매핑을 적용해 핵심 ETL 코드를 수정하지 않고 새로운 공급사 구조 추가

검수 시간이 길어 HTTP 요청이 오래 걸릴 수 있음

Redis + Celery로 검수 작업을 비동기 처리

ETL 결과를 바로 운영 카탈로그에 반영하면 위험함

Preview → 승인 → Promotion 단계로 분리

Preview 이후 데이터가 변경될 수 있음

SHA-256 기반 Preview 검증으로 사용자가 확인한 내용과 실제 적용 내용의 불일치 방지

Promotion 이후 변경 원인을 추적하기 어려움

Promotion History + Audit 기록 추가

잘못 반영한 데이터를 안전하게 되돌리기 어려움

Rollback Preview + Conflict 확인 + DB Transaction으로 복구

Docker 이미지가 로컬에서는 빌드되지만 서버에서 깨질 수 있음

GitHub Actions에서 이미지 빌드 → import → migration → Uvicorn 실행 → /health 200까지 자동 검증

테스트와 품질 관리

최신 정리 기준 일반 테스트:

1042 passed
88 skipped
4 deselected

추가로 다음 흐름을 자동 검증했습니다.

일반 Unit / Integration Test

Redis·Celery Async Inspection E2E

Streamlit Smoke Test

Chromium Browser E2E

AWS Docker Runtime Smoke Test

Alembic Migration 실행 검증

FastAPI /health, /ready 상태 점검

10,000행 데이터 검수 성능도 별도로 측정하여 실행 시간과 메모리 사용량을 기록했습니다.

기술 스택

항목

내용

Backend

Python 3.11, FastAPI

Database

PostgreSQL, SQLAlchemy, Alembic

Data

pandas, CSV, Supplier Profile ETL

Async

Redis, Celery

UI

Streamlit

Test

pytest, AppTest, Chromium Browser E2E

CI

GitHub Actions

Infra

Docker, AWS EC2, AWS RDS

Monitoring

Structured Log, Request ID, /health, /ready

유형

개인 프로젝트

Links

GitHub: https://github.com/psy0635-ctrl/catalogguard-lite

Streamlit Demo: https://catalogguard-lite-p6jtwmdhwqcapphpghfzduo.streamlit.app/

Project Document: https://github.com/psy0635-ctrl/catalogguard-lite/blob/main/docs/portfolio_project.md

2. Waple Worklog MCP Server — 기업 연계 프로젝트

Git 기록과 세션 로그를 근거로 업무일지 초안을 생성하고,사용자가 검토·승인한 내용만 HR SaaS 플랫폼에 등록하는 MCP 서버

프로젝트 배경

미래내일 일경험 프로젝트형 프로그램으로 진행한 유시스(UXIS) × HARP 4인 팀 프로젝트입니다.

8주 동안 AI Report와 MCP 기반 업무 자동화 기능을 개발하였으며, 저는 팀 리드와 MCP 서버 개발을 담당했습니다.

핵심 구현

Git 기록·사용자 메모·세션 로그 기반 업무일지 초안 생성

초안 생성과 실제 SaaS 등록 도구 분리

사용자 검토·수정·승인 이후에만 등록되도록 흐름 설계

작성 근거 라벨([커밋], [사용자 메모], [세션 로그]) 부착

근거가 없는 항목은 임의 생성하지 않고 확인 필요로 분리

Local stdio / Remote Streamable HTTP Transport 지원

ContextVar를 사용한 요청별 API Key·초안 격리

nginx + HTTPS 구성

제한된 서버 권한 환경에서 사용자 단위 systemd 자동 재시작 구성

실제 SaaS 환경 연동 및 라이브 시연

트러블슈팅 기록

성공한 결과뿐 아니라 다음 문제의 원인과 대응 과정도 문서화했습니다.

DNS Rebinding 방지 설정으로 발생한 HTTP 421 오류

TLS 인증서 중간 체인 누락

API Key 평문 노출 문제와 대응

웹 커넥터 연결 실패 원인을 서버 로그로 추적

코드 리뷰 피드백을 반영한 다중 사용자 상태 격리 구조 개선

기술 스택

항목

내용

Backend / AI

Python, MCP Python SDK(FastMCP), LangGraph

HTTP

requests, Streamable HTTP

Test

pytest

Infra

nginx, HTTPS, systemd

유형

4인 팀 프로젝트

역할

팀 리드 · MCP 서버 개발

기간

2026.06.01 ~ 2026.07.26

테스트 기록

23종 — 22 passed, 1 skipped

Links

GitHub: https://github.com/psy0635-ctrl/waple-worklog-mcp-portfolio

Detailed Document: docs/waple-worklog-mcp-상세설명.pdf

Other Projects

대표 프로젝트 외 작업은 사용 기술과 목적 중심으로 간단히 정리했습니다.

프로젝트

핵심 내용

기술

Weather Fit Talk

날씨·상황 조건을 반영하는 로컬 LLM 스타일링 챗봇

Python, Streamlit, Ollama, Gemma

FIT FINDER

체형별 패션 가이드 반응형 웹사이트

HTML5, CSS3, Flexbox, Grid, GitHub Pages

Suyong Portfolio

프로젝트와 기술을 정리한 개인 포트폴리오 웹사이트

HTML5, CSS3, JavaScript, Vercel

SafeTrade

질문 기반 중고거래 사기 위험도 계산 프로그램

Java

C Calculator

함수 분리와 Git 협업을 연습한 5인 팀 계산기

C, GCC, Git, GitHub

Semicolon Team Page

동아리 팀원 및 프로젝트 공유 페이지

HTML5, CSS3, Vercel

Repository Links

Weather Fit Talk: https://github.com/psy0635-ctrl/Weather-Fit-Talk-Local-LLM

FIT FINDER: https://github.com/psy0635-ctrl/HTML_Project

Suyong Portfolio: https://github.com/psy0635-ctrl/Suyong-Portfolio

Semicolon Team Page: https://github.com/hazyala/semicolon-teampage

Engineering Highlights

프로젝트를 통해 다음과 같은 백엔드 문제를 직접 다뤘습니다.

Data Quality

Raw CSV
→ Validation
→ Standardization
→ Inspection
→ Persistence

단순 CRUD가 아니라 잘못된 데이터가 시스템에 들어오는 과정 자체를 제어하는 구조를 구현했습니다.

Safe Data Change

Preview
→ User Approval
→ Transaction
→ Audit
→ Rollback

데이터 변경 자체보다 잘못 변경되었을 때 추적하고 복구할 수 있는가를 고려했습니다.

Async Processing

FastAPI
→ Redis
→ Celery Worker
→ PostgreSQL

오래 걸릴 수 있는 작업을 API 요청과 분리해 처리했습니다.

Test & CI

Code Change
→ pytest
→ Integration / E2E
→ Docker Runtime Check
→ GitHub Actions

로컬에서만 동작하는 코드를 만드는 대신 자동 검증 가능한 상태를 유지하려고 했습니다.

Repository Map

psy0635-ctrl/
├── catalogguard-lite
│   └── Fashion catalog QA / ETL / Promotion / Rollback backend
│
├── waple-worklog-mcp-portfolio
│   └── MCP-based worklog automation server
│
├── Weather-Fit-Talk-Local-LLM
│   └── Local LLM styling chatbot
│
├── HTML_Project
│   └── FIT FINDER fashion guide
│
├── Suyong-Portfolio
│   └── Personal portfolio website
│
├── SafeTrade
│   └── Java console project
│
└── Study-Archive
    └── C / C# / Java / Python / DB / Linux / AI study records

Current Focus

현재는 새로운 프로젝트를 계속 늘리기보다 Python Backend 취업에 직접 연결되는 역량을 깊게 만드는 것에 집중하고 있습니다.

CatalogGuard Lite를 기반으로 FastAPI·PostgreSQL·ETL·비동기 처리 경험 정리

Docker·AWS 배포와 CI/CD 설명력 강화

SQL·DB 성능 개선 및 데이터 처리 역량 보완

코딩 테스트와 CS 기초 병행

LangGraph·MCP 프로젝트 경험 문서화

이력서·포트폴리오 기반 실제 채용 지원

Contact

플랫폼

링크

GitHub

https://github.com/psy0635-ctrl

Portfolio

https://suyong-portfolio.vercel.app

<div align="center">

Build → Test → Deploy → Verify → Document

작게 구현하고, 실제로 검증하고, 문제 해결 과정을 기록합니다.

</div>
