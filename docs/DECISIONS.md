# 의사결정 기록

| 번호 | 날짜 | 결정 | 이유 | 대안 |
| --- | --- | --- | --- | --- |
| D-001 | 2026-11-29 | 문서를 docs/ 아래 목적별 폴더로 재구성, v1 문서는 archive/v1로 이동 | v2 작업과 v1 기록을 분리 | 기존 평면 구조 유지 |
| D-002 | 2026-11-29 | 프론트엔드는 `frontend/`(index.html, src/, assets/, tests/), 백엔드는 `backend/`로 분리. PRD §5.1의 루트 `src/` 구조를 `frontend/` 안으로 이동. 루트 `index.html`은 Phase 1 착수 시 Vercel Root Directory 변경과 함께 이동 | 정적 배포(Vercel)와 Spring Boot 빌드·배포를 독립시키고, Playwright·JUnit 테스트와 문서용/런타임 에셋을 분리 | PRD 원안대로 루트에 `src/`·`assets/`·`tests/` 배치 |
| D-003 | 2026-11-29 | V3 FastAPI AI 서비스(F05)는 루트 `ai/`에 두고 `frontend/`·`backend/`와 나란히 배치. pytest·AI 평가셋도 `ai/` 안에 둠 | Spring Boot(제품 API·최종 정책)와 AI 책임 분리(PLANNING_V3 §4), Python 빌드·의존성·배포를 독립. LLM API 키는 `ai/` 서버 전용 | `backend/` 하위 모듈로 포함, 별도 저장소로 분리 |
