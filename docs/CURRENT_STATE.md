# 현재 상태

> 마지막 갱신: 2026-11-29

## 대상 버전·Phase

- **V2 Phase 0** (기준선·스토리보드·자산 권리·DB 정책): 착수 전
- V3는 V2 이후 착수

## 버전별 상태

| 버전 | 상태 | 핵심 문서 |
| --- | --- | --- |
| v1 | 운영 중. 루트 `index.html` + Supabase 방명록, Vercel 배포 | [archive/v1](archive/v1/) |
| v2 | 기획서·PRD 작성 완료(구현 전 기준안), Phase 0 착수 전 | [PLANNING_V2](planning/PLANNING_V2.md) · [PRD_V2](planning/PRD_V2.md) |
| v3 | 기획서·PRD 작성 완료(개발 전 요구사항) | [PLANNING_V3](planning/PLANNING_V3.md) · [PRD_V3](planning/PRD_V3.md) |

## 완료

- 저장소 폴더·문서 구조 세팅 ([D-001](DECISIONS.md), [D-002](DECISIONS.md), [D-003](DECISIONS.md))

## 다음 작업

- [V2-P0-01](tasks/active.md) `index.html` 현재 구조 정리

## 차단 요소

- 없음 (사용자 결정이 필요한 항목은 [active.md](tasks/active.md)의 `[사용자]` 표시 참조)

## 미해결 위험

- `index.html`을 `frontend/`로 옮길 때 Vercel Root Directory를 함께 바꾸지 않으면 v1 운영 서비스가 중단됨 (D-002, [backlog](tasks/backlog.md))
- 기존 클라이언트의 Supabase 직접 공개 쓰기는 V2 서버 전환 후 제거 대상 (PLANNING_V2 §5)
