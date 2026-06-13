# Suyong Park — Developer Portfolio

<div align="center">

**AI Software Student · Backend · Computer Vision · Web · Database**

배운 것을 코드로 확인하고, 만든 것을 기록으로 남기는 개발자 박수용입니다.<br/>
직접 만들고 오류를 해결하는 과정에서 깊게 배운다고 믿습니다.

[![GitHub](https://img.shields.io/badge/GitHub-psy0635--ctrl-181717?style=flat-square&logo=github)](https://github.com/psy0635-ctrl)
[![Portfolio](https://img.shields.io/badge/Portfolio-suyong--portfolio.vercel.app-000000?style=flat-square&logo=vercel)](https://suyong-portfolio.vercel.app)

</div>

---

## About Me

| 키워드 | 설명 |
|--------|------|
| **Builder** | 배운 내용을 바로 코드로 구현하며 이해합니다. |
| **Explorer** | Backend, AI, Vision, Web, DB를 폭넓게 실험합니다. |
| **Collaborator** | Git 브랜치 전략과 PR 기반 팀 협업을 경험했습니다. |
| **Recorder** | 학습 과정과 결과물을 GitHub에 꾸준히 정리합니다. |

---

## Tech Stack

| 분류 | 기술 |
|------|------|
| **Language** | C, C#, Java, Python |
| **Frontend** | HTML5, CSS3, Responsive UI, Glassmorphism |
| **AI / Vision** | OpenCV, NumPy, Local LLM (Ollama, Gemma), LangChain, Claude API |
| **Backend / DB** | FastAPI, MySQL, SQL, Database Modeling, Pandas |
| **System** | Linux, Git, GitHub |
| **Deploy** | Vercel, GitHub Pages |
| **Tools** | Streamlit, DuckDuckGo Search API |

---

## Projects

### 1. 유시스(Waple) — HR AI Report System

> HR SaaS 플랫폼 Waple에 AI 리포트 기능을 붙이는 실무형 팀 프로젝트

**개발 배경**

미래내일 일경험(프로젝트형) 프로그램으로, 유시스(UXIS)의 HR SaaS 플랫폼 Waple에 AI 기능을 추가하는 실무 프로젝트입니다. 직원 데이터를 AI가 분석하여 관리자에게는 주간 조직 현황, 근로자에게는 개인 인사이트 리포트를 자동으로 생성하는 것이 목표입니다.

**담당 역할**

팀장 + LLM 개발 담당. Claude API를 활용한 리포트 생성 파이프라인 설계 및 구현을 맡았습니다.

**주요 구현**

- Claude API를 활용한 HR 데이터 기반 AI 리포트 자동 생성
- 점수 → 원인 → 액션까지 연결되는 3단계 리포트 구조 설계
- FastAPI 기반 API 서버 구축 (`POST /api/report/admin`, `POST /api/report/individual`)
- LangChain으로 LLM 호출 흐름 관리
- MCP(Model Context Protocol) 활용 업무일지 자동 작성 기능 개발

**설계 특징**

단순 점수 출력이 아닌 "점수 → 원인 → 액션 제안"까지 연결되는 구조를 설계했습니다. 관리자는 조직 전체의 목표/근태/업무일지 종합 상태를, 근로자는 번아웃 리스크·이직 리스크·개선 제안을 AI 리포트로 받아볼 수 있습니다.

| 항목 | 내용 |
|------|------|
| **Stack** | Python, LangChain, FastAPI, Claude API, Pandas, HuggingFace, FAISS |
| **유형** | 4인 팀 프로젝트 (팀장) |
| **기간** | 2026.06.01 ~ 07.26 (8주) |
| **GitHub** | https://github.com/uxis-co-kr/2026-uxis-mirae |

---

### 2. FIT FINDER — Body-based Fashion Guide Web

> 체형을 기준으로 어울리는 핏과 피해야 할 스타일을 안내하는 패션 가이드 웹사이트

**개발 배경**

웹프로그래밍기초 수업에서 배운 HTML/CSS를 실제 서비스 형태로 구현해보고 싶었습니다. 단순 과제 수준을 넘어, Glassmorphism Dark UI와 Video Background를 적용해 완성도 있는 정적 웹사이트를 제작했습니다.

**주요 구현**

- 6가지 체형(Triangle, Inverted, Rectangle, Hourglass, Round, Trapezoid) 선택 시스템
- 체형별 DO / DON'T 스타일 가이드 카드 구성
- Glassmorphism Dark UI + Video Background Hero 디자인
- Grid Layout 기반 체형 선택 화면 구성
- GitHub Pages 배포

**배운 점**

- CSS Grid와 Flexbox를 실제 레이아웃에 적용하는 방법
- Glassmorphism 효과 (`backdrop-filter`, `rgba`) 구현
- 멀티 페이지 정적 사이트 구조 설계 (`index`, `guide`, `tips`, `about`)

| 항목 | 내용 |
|------|------|
| **Stack** | HTML5, CSS3, Flexbox, Grid, GitHub Pages |
| **유형** | 개인 프로젝트 |
| **슬로건** | "Fit is not size. Fit is balance." |
| **GitHub** | https://github.com/psy0635-ctrl/HTML_Project |

---

### 3. Suyong Portfolio

> 순수 HTML/CSS만으로 제작한 싱글 페이지 포트폴리오 웹사이트

**개발 배경**

포트폴리오를 링크로 공유할 때 바로 열 수 있는 웹 형태가 필요했습니다. 외부 프레임워크 없이 기초 기술만으로 완성도 있는 결과물을 만들 수 있다는 것을 직접 확인하고 싶었습니다.

**주요 구현**

- 하단 고정 네비게이션 클릭 시 Info / Projects / Stacks 섹션 전환
- `display: none / flex` 토글 방식으로 JS 없이 섹션 가시성 제어
- CSS `opacity + translateY` 페이드인 애니메이션 적용
- 태블릿(1024px) · 모바일(768px) 미디어 쿼리 반응형 대응
- `backdrop-filter: blur()` 글래스모피즘 네비게이션 효과

**트러블슈팅**

섹션 전환 시 이전 섹션이 사라지지 않는 문제가 발생했습니다. 기본값을 `display: none`으로 설정하고 `active` 클래스에서만 `display: flex`를 적용하는 방식으로 해결했습니다.

| 항목 | 내용 |
|------|------|
| **Stack** | HTML5, CSS3, Google Fonts, Font Awesome, Vercel |
| **유형** | 개인 프로젝트 |
| **배포** | https://suyong-portfolio.vercel.app |
| **GitHub** | https://github.com/psy0635-ctrl/Suyong-Portfolio |

---

### 4. Semicolon Team Page

> Semicolon 동아리 팀원 소개와 프로젝트 링크를 정리한 팀 페이지

**개발 배경**

팀 프로젝트 결과물을 외부에 공유할 수 있는 온라인 페이지가 필요했습니다.

**주요 구현**

- 팀원 소개 섹션 및 GitHub Repository 링크 연결
- Vercel 정적 웹사이트 배포

| 항목 | 내용 |
|------|------|
| **Stack** | HTML5, CSS3, GitHub, Vercel |
| **유형** | 팀 프로젝트 (Semicolon 동아리) |
| **배포** | https://semicolon-teampage.vercel.app |
| **GitHub** | https://github.com/hazyala/semicolon-teampage |

---

### 5. Weather Fit Talk

> 날씨와 상황에 맞는 옷차림을 추천하는 로컬 LLM 기반 AI 스타일링 챗봇

**개발 배경**

OpenAI · Gemini API Key 없이 로컬 환경에서 실행 가능한 AI 챗봇을 만들고 싶었습니다. 외부 API 비용 없이 LLM을 직접 구동하는 방식을 실험하는 것이 목적이었습니다.

**주요 구현**

- Ollama + Gemma 모델로 로컬 LLM 구동 (API Key 불필요)
- 사이드바에서 기온 · 바람 · 상황 · 스타일 조건 입력
- DuckDuckGo 검색 옵션으로 최신 날씨 정보 보완
- 사용자 사이드바 조건이 채팅 입력보다 우선 반영되는 구조 설계

| 항목 | 내용 |
|------|------|
| **Stack** | Python, Streamlit, Ollama, Gemma, DuckDuckGo Search |
| **유형** | 개인 프로젝트 |
| **GitHub** | https://github.com/psy0635-ctrl/Weather-Fit-Talk-Local-LLM |

---

### 6. SafeTrade — 중고거래 사기 위험도 체크 프로그램

> 5가지 질문으로 중고거래 사기 위험도를 점수로 계산해주는 Java 콘솔 프로그램

**개발 배경**

중고거래 사기 피해가 늘어나고 있지만 거래 전 위험 요소를 체크할 수 있는 간단한 도구가 없었습니다. 실생활 문제를 프로그램으로 해결하는 경험을 목적으로 Java 수업 과제로 제작했습니다.

**주요 구현**

- 전자기기 · 의류 · 티켓 · 게임용품 · 기타 5개 카테고리 물품 선택
- 위험 패턴 5가지(저가, 직거래 거부, 선입금, 정보 부족, 급유도)를 질문으로 점수화
- 총점 기준 4단계 위험 등급 출력 (안전 / 주의 / 위험 / 매우 위험)
- 배열 + for문 조합으로 질문 목록과 점수를 구조화하여 관리

**배운 점**

- Scanner, switch문, 배열, for문, if문을 실제 프로그램에 통합 적용
- 단순 계산이 아닌 실생활 문제를 프로그램으로 해결하는 설계 경험

| 항목 | 내용 |
|------|------|
| **Stack** | Java, IntelliJ IDEA |
| **유형** | 개인 프로젝트 (수업 과제) |
| **GitHub** | https://github.com/psy0635-ctrl |

---

### 7. C Calculator — 5인 팀 사칙연산 계산기

> C언어 함수 분리와 Git 협업 방식을 실습하기 위한 팀 프로젝트

**팀 구성 및 담당**

| 이름 | 담당 | 구현 내용 |
|------|------|----------|
| 민재 | 덧셈 `+` | `add()` 함수 구현 |
| 가영 | 뺄셈 `-` | `add(a, -b)` 방식으로 구현 |
| 형준 | 곱셈 `*` | `multiply()` 함수 구현 |
| **수용** | **나눗셈 `/`** | **`divide()` + 이중 예외처리 구현** |
| 석현 | 나머지 `%` | `modulo()` 함수 구현 |

**나눗셈 구현 — 이중 방어 구조 (수용 담당)**

main에서 1차 검사, `divide()` 내부에서 2차 검사를 적용했습니다. 함수가 다른 곳에서 재사용될 때도 독립적으로 안전하게 동작하도록 설계했습니다.

**트러블슈팅**

병합 후 팀원마다 다른 코드 스타일로 인해 중괄호 누락 컴파일 에러가 발생했습니다. GCC 에러 메시지의 줄 번호를 기준으로 추적해 해결했고, 이후 팀 내 코딩 컨벤션을 사전 통일했습니다.

| 항목 | 내용 |
|------|------|
| **Stack** | C, GCC, Git, GitHub |
| **유형** | 5인 팀 프로젝트 |
| **GitHub** | 추가 예정 |

---

## Study Tracks

| 분야 | 학습 내용 |
|------|----------|
| **C** | 변수, 조건문, 반복문, 함수, 배열, 포인터, 파일 입출력 |
| **C#** | 클래스, 객체, 생성자, 메서드, 접근 제어자 |
| **Java** | 기본 문법, 클래스 설계, Scanner, switch, 배열 |
| **Python** | 데이터 처리, 자동화, OpenCV, NumPy, Matplotlib, LangChain |
| **HTML / CSS** | Semantic Tag, Flexbox, Grid, Glassmorphism, 반응형 디자인 |
| **Database** | SELECT, INSERT, UPDATE, DELETE, JOIN, 정규화 |
| **OpenCV** | Morphology, Histogram, Thresholding, 이미지 변환 |
| **Linux** | ls, cd, grep, find, chmod, ps, kill, vi |
| **AI / LLM** | Local LLM (Ollama), LangChain, Claude API, RAG 구조 |

---

## Activities

| 활동 | 상태 |
|------|------|
| 미래내일 일경험 — 유시스 Waple AI Report | 진행 중 (2026.06~07) |
| Semicolon 개발 동아리 활동 | 진행 중 |
| Linux Master 2급 학습 | 진행 중 |
| Git & GitHub 협업 흐름 학습 | 진행 중 |
| AI / LLM / RAG 구조 학습 | 탐색 중 |
| 데이터 공모전 아이디어 기획 | 기획 중 |
| GitHub Pages · Vercel 배포 | 완료 |

---

## Repository Map

```
psy0635-ctrl/
├── Suyong-Portfolio           # 포트폴리오 웹사이트 (HTML/CSS)
├── HTML_Project               # FIT FINDER 패션 가이드 웹 (HTML/CSS)
├── Weather-Fit-Talk-Local-LLM # 로컬 LLM 스타일링 챗봇 (Python)
├── SafeTrade                  # 중고거래 사기 위험도 체크 (Java)
├── C-Calculator               # 5인 팀 계산기 (C)
└── Study-Archive              # 언어별 학습 기록
    ├── C / CSharp / Java / Python
    ├── HTML_CSS / Database
    ├── OpenCV / Linux
    └── AI_LLM
```

---

## Goals

**단기**
- 유시스 Waple AI Report 프로젝트 완성 (2026.07)
- GitHub 포트폴리오 완성도 강화
- FIT FINDER JavaScript 인터랙션 추가

**장기**
- AI + Web 융합 개발자로 성장
- Computer Vision 심화 학습
- 실무에 가까운 문제 해결 역량 확보

---

## Contact

| 플랫폼 | 링크 |
|--------|------|
| **GitHub** | https://github.com/psy0635-ctrl |
| **Portfolio** | https://suyong-portfolio.vercel.app |

---

<div align="center">

> 꾸준한 학습과 기록은 가장 강력한 성장 루틴이다.

**Build small. Learn deep. Keep shipping.**

</div>
