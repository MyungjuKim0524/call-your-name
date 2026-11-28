# 진행 중인 작업

## V2 Phase 0: 기준선·스토리보드·자산 권리·DB 정책

- 근거: [PRD_V2 §8·§9](../planning/PRD_V2.md#8-phase별-구현-및-산출물), [PLANNING_V2 §6](../planning/PLANNING_V2.md#6-로드맵-및-범위-통제)
- 선행 조건: 없음
- Phase 완료 기준: 기존 3개 경로의 기준선 확보, P0 범위 승인
- 상태 값: `TODO` / `IN_PROGRESS` / `BLOCKED` / `DONE` (AGENTS.md R23)
- `[사용자]`: 사용자가 결정·승인해야 하는 항목. 에이전트는 임의로 확정하지 않습니다.

### 1. 기존 서비스 기준선

| ID | 작업 | 수용 기준 | 기록 위치 | 의존성 | 상태 |
| --- | --- | --- | --- | --- | --- |
| V2-P0-01 | `index.html` 현재 구조 정리 | `currentStep`, `SCENARIO_GRAPH`, `renderFSMNode()`, `PHOTOCARD_ROUTES`, `GuestbookRepository`, Tone.js 사용 위치를 코드 근거와 함께 기록 | `docs/ARCHITECTURE.md` "v1 현황" | — | TODO |
| V2-P0-02 | A/B/C 장면 흐름·대사 목록화 | 세 경로의 장면 순서(PRD 기준 A 6→7→13, B 8→9→13, C 10→11→12→13)와 화자·핵심 대사가 코드와 일치 | `docs/design/SCENARIO.md` | V2-P0-01 | TODO |
| V2-P0-03 | 기준선 수동 테스트 | 이름 치환, 세 분기, 포토카드 PNG 저장(iOS Safari 포함), 방명록, BGM·효과음의 실제 결과 기록. 미실행 항목은 NOT RUN | `docs/testing/TEST_REPORT.md` "V2 Phase 0 기준선" | V2-P0-02 | TODO |

### 2. 기존 데이터·DB

| ID | 작업 | 수용 기준 | 기록 위치 | 의존성 | 상태 |
| --- | --- | --- | --- | --- | --- |
| V2-P0-04 | 운영 `guestbook` 백업 `[사용자]` 실행 승인 | 읽기 전용 백업 완료, 파괴적 SQL 미실행. 백업 파일은 저장소에 커밋하지 않음 | `docs/CURRENT_STATE.md` (백업 일시·위치만) | 승인 | TODO |
| V2-P0-05 | 운영 스키마와 `supabase/schema.sql` 대조 | 테이블·RLS·권한 차이 목록 | `docs/ERD.md` "v1 현황" | — | TODO |
| V2-P0-06 | 클라이언트 → Supabase 공개 쓰기 경로 확인 | 현재 공개 쓰기 범위와 V2 전환 시 제거 대상 기록 | `docs/SECURITY.md` | V2-P0-05 | TODO |

### 3. 자산 권리 목록

| ID | 작업 | 수용 기준 | 기록 위치 | 의존성 | 상태 |
| --- | --- | --- | --- | --- | --- |
| V2-P0-07 | 자산 출처·이용 조건 목록 | 음원·효과음·그래픽·폰트·라이브러리별 출처와 권리 상태(확인 / 미확인) | `docs/assets/RIGHTS.md` (신규) | V2-P0-01 | TODO |
| V2-P0-08 | 콘서트 음원 후보 정리 | 후보 2~3곡의 출처, 권리 상태(자체 합성 / 권리 확인 / 미확인), 서비스 삽입·재배포 조건 | `docs/assets/RIGHTS.md` | V2-P0-07 | TODO |

### 4. 화면 흐름·스토리보드

| ID | 작업 | 수용 기준 | 기록 위치 | 의존성 | 상태 |
| --- | --- | --- | --- | --- | --- |
| V2-P0-09 | S01~S16 화면 목록·이동 경로 | 오두막 허브(S02)에서 모든 활동의 진입·복귀 경로 표시 | `docs/design/SCREEN_DESIGN.md` | V2-P0-02 | TODO |
| V2-P0-10 | A/B/C 인터랙션·연결 대사안 | 후보(걱정 풍선 / 구름 걷기 / 창문 닦기·차 우리기)별 원본 대사 연결과 스킵 경로 | `docs/design/INTERACTION_DESIGN.md` | V2-P0-02 | TODO |
| V2-P0-11 | 인터랙션·신규 대사 확정 `[사용자]` | 사용자 승인 | `docs/DECISIONS.md` | V2-P0-10 | TODO |

### 5. 사용자 결정 사항 (PRD_V2 §9)

결정 결과는 `docs/DECISIONS.md`에 기록합니다.

| ID | 결정 | 비고 | 상태 |
| --- | --- | --- | --- |
| V2-P0-12 | 병편지 자유 입력 공개 여부 `[사용자]` | 불가 시 준비 문구 / 읽기 전용 축소 모드 | TODO |
| V2-P0-13 | 기존 방명록 이관 여부 `[사용자]` | V2-P0-04 백업 이후 | TODO |
| V2-P0-14 | 병편지 보존·삭제 기간 `[사용자]` | — | TODO |
| V2-P0-15 | 무료 백엔드 호스팅 선택 | 조사: 에이전트(최신 공식 요금표 기준), 선택: `[사용자]` | TODO |
| V2-P0-16 | 콘서트 음원 채택 `[사용자]` | V2-P0-08 이후 | TODO |
| V2-P0-17 | P0 범위 최종 승인 `[사용자]` | 위 결정 이후 | TODO |

### 6. 마무리

| ID | 작업 | 수용 기준 | 상태 |
| --- | --- | --- | --- |
| V2-P0-18 | Phase 0 인계 | `docs/CURRENT_STATE.md` 갱신, 상세 기록을 `docs/archive/v2/phase-00.md`에 작성, 이 목록을 V2 Phase 1 작업으로 교체 | TODO |
