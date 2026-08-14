# GIL 통합본 v1.7.2 (2026-07-25)

법무 4스킬 디벨롭 — **조사 심도 3모드·소요 사전 고지**와 **정보원 접근 제약(재시도 상한)** 을 규칙화했다.
기준선 v1.7.1, 스킬 수 196 유지(신규 스킬 0).

## 배경

v1.7.2 이전에 도입한 「법률 인용 5규칙」의 (a) "원문 확인 1순위" 관할 프로필과
(b) "VERIFIED 아니면 폐기"(3분류·회색지대 금지)가 결합하면, 원문이 기술적으로 접근 불가능한 관할에서
에이전트가 대체 엔드포인트를 무한 순회한다. 실측: UZ 노동법 질의 1건에 원문 시도 **132회·21분**,
상당수 "미확인" 종료. lex.uz는 조문 본문을 JavaScript로 렌더링해 자동 fetch로는 목차만 회수된다.

## 변경 사항

### 신규 정본 (법무 4스킬 공용, contract-review/references/)
- **research-depth-modes.md** — 조사 심도 3모드(⚡Quick 3~5분 / ◐Standard 8~12분 / ◆Deep 20분+),
  **8분 초과 시 착수 전 1회 소요 고지·선택 (HARD)**, 무인 실행 시 Standard 기본,
  문서 체인 2단 분리(조사 확정 → "이 내용으로 DOCX만" 시 뒷단만 실행).
- **source-access-notes.md** — 정보원 접근 실무. **원문 확보 시도 상한: 정보원 3곳·총 5회 (HARD)**,
  PDF 엔드포인트 추측·미러·언어판 순회 금지, lex.uz JS 렌더링 제약 명시,
  UZ 2차 출처 우선순위(norma·kadrovik·buxgalter → regulation.gov.uz → 매체 → 한국어 자료),
  원문 필요 시 사용자 붙여넣기·브라우저 도구 요청, 실패 항목 기록 의무.
  한국 질의(korean-law MCP·law.go.kr)에는 본 상한을 확대 적용하지 않는다.

### 수정
- **legal-citation-rules.md** — 인용 무결성 **3분류 → 4분류**. `SECONDARY`(2차 출처 확인·원문 미대조,
  `⚠ 원문 재확인 필요` 병기) 신설. Quick·Standard 허용, Deep 불허. 관할 프로필에 lex.uz 제약·재시도 상한 반영.
- **contract-review · nda-triage · legal-risk · compliance-check** — 인용 5규칙 요약 3번을 4분류로 갱신,
  「정보원 접근 상한(HARD)」·「조사 심도·소요 사전 고지(HARD)」 섹션 추가.
  nda-triage는 기본 모드를 ⚡Quick으로 명시(5분 신속 포맷 목적).
- **agents/legal-review-coordinator.md** — 워크플로우 0단계 「심도 모드 확인·소요 사전 고지」 신설,
  Quick 단축 경로(단일 스킬만 실행), 문서화 분리, 원문 재시도 상한 명시.

### 버전
- plugin.json ×1 + SKILL.md ×196 전 지점 **1.7.2**.

## 게이트

- 버전 전수 일치 197/197 PASS (skill-tester 본문의 `<plugin-version>` 템플릿 문자열은 대상 외)
- `gil-<domain>:` 잔존 0 (평탄화 유지) PASS
- `moai-[a-z]+[:/]` 잔존 0 PASS
- zip 슬래시 경로·`.claude-plugin/plugin.json` 최상위·dir==name·kebab·예약어 0 PASS

## 롤백

`gil-unified-v1.7.1-clean/` (직전 통합본)
