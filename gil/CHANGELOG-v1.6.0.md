# GIL 통합본 v1.6.0 — 연구 스킬 디벨롭 (2026-07-03)

> 개인 사적 사용·로컬 전용(NC-ND 2차저작물). 공개 재배포 금지.

## 요약
`연구자동화_플레이북.md`(사용자 본인 저작물 → **GIL 오리지널**, 별도 attribution 불필요)에서 실전 확립한 아카이벌 실증·계량·강건성·실행공학 SOP를 연구 스킬군에 반영. 신규 스킬 없이 기존 4종을 심화하고 reference 5종을 추가.

## 변경 내역

### 심화 스킬 4종 (SKILL.md 섹션 추가)
- **research-methodology**: `## 실증·아카이벌 연구 & Kill-fast 프로토콜` 추가 (Kill-fast 게이트·코퍼스-질문 정합·주제 bake-off·정책충격 DiD·정직성 원칙).
- **research-analysis**: `## 인과 식별 강건성 3+2종세트 + 정직한 재프레이밍`(기업FE→event-study→stacked→placebo→판정), `## 아카이벌 데이터 파이프라인·NLP 측정·샌드박스 실행` 추가.
- **devil-review**: `#### Layer 2.5: 실증·인과 식별(archival·준실험)` 체크리스트 + 선제 방어 지침 추가.
- **research-assistant**: `## 실증연구 착수 시(아카이벌·계량)` Kill-fast 안내 추가.

### 신규 reference 5종
- research-methodology/references/**archival-empirical-playbook.md** (75줄)
- research-analysis/references/**causal-robustness-sop.md** (70줄)
- research-analysis/references/**data-pipeline-traps.md** (53줄, 11대 함정)
- research-analysis/references/**nlp-measurement-quagmire.md** (43줄)
- research-analysis/references/**sandbox-execution-patterns.md** (75줄)

### 버전
- plugin.json 1.5.0 → **1.6.0**, SKILL.md 189종 전부 1.6.0 일괄.

## 안전장치 준수
- 플레이북 함정 #8(대량호출 후 접근제한)은 "공유기 재부팅으로 IP 변경"(차단 우회 오해 소지)을 제거하고 **공식 API 키·요청 throttle·지수백오프·재개·야간분할**로 정직하게 재프레이밍해 수록.

## 검증 게이트 (전수 PASS)
- SKILL.md 189×1.6.0 일치, plugin.json 1.6.0 일치.
- `moai-[a-z]+[:/]` 교차참조 = 0건.
- 편집 4종의 gil: 교차참조 15종 전부 실재 스킬로 해결.
- frontmatter YAML 189종 유효(오류 0).
- gil.plugin zip: 슬래시 경로만·백슬래시 0·비ASCII 경로 0·예약어 'claude' 스킬 0·dir==name·중복 0·plugin.json 최상위. testzip OK, 828 엔트리.

## 롤백 경로
- `gil-unified-v1.5.2-clean/` (직전본, 1.5.0)
