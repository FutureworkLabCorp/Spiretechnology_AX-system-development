# 스파이어테크놀로지 AX 시스템 개발

> 기획/스펙 문서 및 와이어프레임 관리 레포지토리

## 외부 링크

| 리소스 | 링크 |
|--------|------|
| Linear 프로젝트 | [[외주] 스파이어테크놀로지 (SPI)](https://linear.app/futureworklab-workspace/project/외주-스파이어테크놀로지-spi-fb4880a2df7f) |
| Linear 프로젝트 (전신 데모) | [Spire Technology](https://linear.app/futureworklab-workspace/project/spire-technology-ef70ec62f4e0) |
| Google Drive | [SPI 공유 드라이브](https://drive.google.com/drive/u/0/folders/1HQPeqLY-LfdpNR4WW0VWJ2kOM7_D28kO) |

## 디렉토리 구조

```
.
├── docs/                          # 기능별 PRD 및 QA 문서
│   ├── PRD_01_수집전처리.md        # D-01~D-03: 파싱, 청킹, 메타데이터 추출
│   ├── PRD_02_그래프구축.md        # C-01~C-05: 온톨로지, 엔티티 추출, 커뮤니티
│   └── QA_02_그래프구축.md         # C-01~C-05 QA 체크리스트 (60+ 테스트 케이스)
│
├── wireframes/                    # UI 와이어프레임 및 IA
│   ├── axflow_gui_overview_v3.html # GUI 와이어프레임 (최신)
│   ├── screen_detail_spec_v3.html  # 화면별 상세 스펙
│   ├── rbac_access_control.html    # RBAC 접근 제어 시각화
│   └── axflow_ia_v3.csv           # 컴포넌트 IA 명세 (203개 항목)
│
├── 고객사전달파일/                   # 고객사에 전달한 공식 산출물
│   ├── Policy_AXFlow_v1.md        # 기능정책서 (12개 섹션)
│   ├── PRD_AXFlow_v1.html         # PRD (HTML)
│   ├── SPI_기능정책서_v1.0.xlsx
│   ├── SPI_IA_v1.0.xlsx
│   └── index.html                 # GitHub Pages 인터랙티브 와이어프레임
│
├── docs/updates/                  # 개발 진행 업데이트
│
└── WBS.png                        # WBS 다이어그램
```

## 문서 가이드

### PRD (Product Requirements Document)

| 파일 | WBS 범위 | 주요 내용 |
|------|---------|----------|
| [`docs/PRD_01_수집전처리.md`](docs/PRD_01_수집전처리.md) | D-01 ~ D-03 | 멀티 포맷 파싱, 의미론적 청킹, 메타데이터 자동 태깅 |
| [`docs/PRD_02_그래프구축.md`](docs/PRD_02_그래프구축.md) | C-01 ~ C-05 | 온톨로지 정의, 엔티티/관계 추출, 실체 연결, 커뮤니티 감지, 요약 및 임베딩 |

### QA 체크리스트

| 파일 | 범위 | 테스트 수 |
|------|------|----------|
| [`docs/QA_02_그래프구축.md`](docs/QA_02_그래프구축.md) | C-01 ~ C-05 | 60+ 건 (P0/P1/P2 우선순위) |

### 기능정책서

[`고객사전달파일/Policy_AXFlow_v1.md`](고객사전달파일/Policy_AXFlow_v1.md) — 화면별 인터랙션 규칙, 상태 전이, 예외 처리 정의.

| 섹션 | 내용 |
|------|------|
| §3 Chat | 에이전트 선택, AI 응답, 피드백, 추론 경로, 참조 자료 |
| §4 Library — Documents | 문서 상태 6단계, 원본 뷰어, OCR 검수, 메타데이터, 그래프 연결 |
| §5 Library — Materials | OCR 문서양식 관리, 제목 계층, 감지 설정 |
| §6 Library — Database | DB 관리, 필드 타입, CSV/JSON 임포트 |
| §7 Library — Knowledge Graph | 그래프 탐색기, 노드 편집, 온톨로지 관리, 사전/매핑, 변경 이력 |
| §8 Settings — Administration | 도메인 워크스페이스, MCP 도구 관리 |
| §9 Settings — Pipeline | 파싱/청킹 설정, 파이프라인 모니터 |
| §10 Settings — Monitoring | 토큰/비용 KPI, Ragas 성능 지표 |
| §11 Settings — Agents | 메인/서브 에이전트, 프롬프트, 파라미터, 스킬/훅/커맨드, A/B 테스트 |
| §12 Settings — RBAC | 4단계 역할(L4~L1), 문서 보안등급(일반~극비), 접근 감사 로그 |

### 와이어프레임

| 파일 | 설명 |
|------|------|
| `wireframes/axflow_gui_overview_v3.html` | GUI 와이어프레임 (최신 v3) |
| `wireframes/screen_detail_spec_v3.html` | 화면별 상세 스펙 |
| `wireframes/rbac_access_control.html` | RBAC 접근 제어 시각화 |
| `wireframes/axflow_ia_v3.csv` | IA 컴포넌트 명세 (203개 항목) |
| `고객사전달파일/index.html` | GitHub Pages 인터랙티브 와이어프레임 |

## 개발 진행 업데이트

| 날짜 | 요약 |
|------|------|
| [2026-03-30](docs/updates/2026-03-30.md) | 수집/전처리(D) 완료, 그래프 구축(C) 진행 중, LightRAG 업그레이드, vLLM 인프라 검토 |

## 마일스톤

| 마일스톤 | 주요 내용 |
|----------|----------|
| MVP 알파 릴리즈 | 핵심 파이프라인 (파싱 → 청킹 → 추출 → 검색) + 관리 UI |
| 8월 릴리즈 | 커뮤니티 감지, 성능 평가, 시각화, RBAC |
| 10월 릴리즈 | 증분 업데이트, 글로벌 검색, MCP GUI, 피드백 루프 |
