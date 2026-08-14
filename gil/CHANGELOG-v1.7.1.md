# GIL 통합본(gil) CHANGELOG — v1.7.1 (2026-07-07)

패치 릴리스 — 스킬 수 변동 없음 (196 유지).

## 정비
- **출처 표기 제거**: gil-creative 계열의 외부 유래 표기(설계서·레퍼런스 워크플로우·CIS 자원 언급)를 전부 제거. gil-creative는 GIL 오리지널로 단일 표기. (CHANGELOG-v1.7.0 2곳 · creative-wizard/creative-architect SKILL.md 2곳 · uz refs 3곳)
- **끊긴 교차참조 10건 수정** (v1.6.0 이전 잔존분):
  - `gil:nano-banana` ×4 → `gil:gemini-3-image-prompt` (ai-slop-reviewer·marketplace-olx·marketplace-uzum)
  - `gil:commerce-review-aggregator` ×2 → `gil:commerce-voc-triage` (marketplace-uzum)
  - `gil:commerce-order-summary` → `gil:commerce-morning-brief` · `gil:course-curriculum-design` → `gil:course-operations-manual` (mcp-connector-setup)
  - `gil:gil-content` 이중 접두 1건 → 실존 문서 스킬 나열로 교체 (project)
  - `../../gil:skills/...` 깨진 상대경로 4건 → 올바른 `../<skill>/...` 경로 (data-visualizer·html-report)
- 버전 전 지점 v1.7.0 → **v1.7.1** (plugin.json ×1 + SKILL.md ×196).

## 게이트
- gil-도메인: 평탄화 0 · moai 0 · 끊긴 교차참조 0(재검증) · 외부 브랜드 표기 0 · zip 슬래시/예약어/dir==name PASS.

## 롤백
- `gil-unified-v1.7.0-clean/` (직전 통합본).
