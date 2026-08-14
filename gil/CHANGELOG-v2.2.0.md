# CHANGELOG — gil v2.2.0 (2026-08-14)

## 신규 스킬 2종 (GIL 오리지널, 146→148)

- **problem-solving** — PSA(Problem Solving Approach) 기반 문제 구조화: Cynefin 라우팅 → SCQ·Key Question → 이슈화(표준 문형+3-Test: Fact/Fork/Action) → 로직트리(5유형·MECE/Actionable/Relevant 게이트) → 가설·QDT → Work Plan 6컬럼. 산출물 등급 ⚡◐◆ 정합. references 5종(psa-core·issue-gates·tree-patterns·templates·uz).
- **research-verify** — 하네스형 리서치 실행·검증: 내부 파일 교차 분석 → 외부 리서치(출처 병기·[미검증]/[추정] 태그) → 3중 검증(팩트·출처·논리) → Red 반론(일반론 불인정) → 사람 승인 게이트 → 조건부 결론. 출처 등급 3분류는 공용 인용 4분류·조사 심도 3모드와 정합. references 3종(verification-loop·source-grading·uz).
- 출처: 사내 PSA·AI 리서치 교육자료(전정우, IQVIA, 2026-08) 방법론 재구성(개인 로컬 전용) + Minto·Conn&McLean·Rasiel&Friga·아타카 카즈토·우치다 카즈나리·Snowden·Kepner-Tregoe clean-room 반영.

## 유기적 연동 (기존 자산 10건 최소 편집)

- 스킬 8종 말미에 "연계 스킬" 섹션 추가: ai-diagnostic·product-brainstorming·consulting-brief·strategy-planner·market-analyst·devil-review·validate-data(책임 경계 보강)·tutor-research
- 에이전트 2종에 신규 라우팅 추가: business-plan-coordinator(착수 시 문제 정의 선행·근거 검증), research-scout-coordinator(비즈니스 리서치 분기)

## 버전

- gil 번들만 2.1.0 → 2.2.0 (plugin.json ×1 + SKILL.md ×148 전 지점). gil-creative(96)·gil-commerce(54)는 변경 없음 — 2.1.0 유지.
- 롤백: `gil-bundles-v2.1.0-clean/`
