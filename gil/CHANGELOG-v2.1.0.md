# CHANGELOG — GIL v2.1.0 (2026-08-11)

## 요약
anthropics/knowledge-work-plugins@2cf4294(Apache-2.0) 2단계 반영 — 후보 M~V 전체.

## 신규 50스킬 (246→296: gil 146 / gil-creative 96 / gil-commerce 54)
- **gil-commerce +17 (small-business)**: monday/friday-brief·month-heads-up·business-pulse·cash-flow-snapshot·invoice-chase·plan-payroll·lead-triage·call-list·crm-cleanup·customer-pulse-check·quarterly-review·sales-brief·price-check·tax-prep·ticket-deflector·smb-onboard
- **gil +26**: data 4(sql-query-writer·statistical-analysis·validate-data·build-dashboard) · productivity 2(task-management·work-memory) · sales 6(account-research·call-prep·call-summary·pipeline-review·sales-forecast·draft-outreach) · finance 3(journal-entry·reconciliation·audit-support) · legal 4(legal-brief·legal-response·signature-request·vendor-check) · HR 6(comp-analysis·org-planning·people-report·policy-lookup·recruiting-pipeline·interview-prep) · PM 4(sprint-planning·metrics-review·stakeholder-update·product-brainstorming) · enterprise-search 1(5스킬 통합)
- **gil-creative +3 (design)**: accessibility-review·design-critique·ux-copy

## 기존 25스킬 방법론 흡수
margin-calculator·close-management·contract-review·escalation-manager·campaign-planner·content-calendar·employment-manager(2)·data-explorer·data-visualizer·daily-briefing·proposal-writer·market-analyst·ux-researcher·financial-statements·variance-analysis·compliance-check·legal-risk·nda-triage·meeting-facilitator·roadmap-manager·spec-writer·design-system-prep·design-handoff 등 — 각 SKILL.md `## 흡수 방법론` 섹션 참조.

## 공통 처리
전 신규 스킬: 한국화 헤더(한국 실무 재맥락+도구 일반화) + UZ refs 1:1(+50=191) + origin 메타 + 책임 경계 명문. 미국 SaaS 커넥터 의존은 방법론 계승으로 일반화. 버전 전 지점 2.1.0(296+3). description 꺾쇠 금지 게이트 신설.

## 롤백
`gil-bundles-v2.0.0-clean/` + `gil-upload-v2.0.0/`
