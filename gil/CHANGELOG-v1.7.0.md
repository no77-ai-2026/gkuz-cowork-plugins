# GIL 통합본(gil) CHANGELOG — v1.7.0 (2026-07-06)

## 신규: 글로벌 광고 크리에이티브 마법사 (gil-creative 계열) — 7 스킬 추가 (189 → 196)

**GIL 오리지널**(자체 설계). 하나의 브리프로 상세페이지·카드뉴스·
포스터·인쇄물을 멀티 포맷·멀티 마켓으로 제작. 텍스트 지능(카피·구성·후기분석·현지화)은
Claude 내재, **이미지 생성만 OpenAI/Gemini BYOK**.

| 스킬(gil:) | 역할 |
|---|---|
| creative-wizard | 코디네이터 — 브리프 인터뷰·라우팅·히어로 승인 게이트 |
| creative-architect | 핵심 IP — 감정 여정 8단계 + 카피 방법론 10종 → CreativeSpec(언어 병렬 RU/UZ/KR) |
| market-profile-engine | 국가·산업 현지화 프로필(UZ/CIS·RU·KR 사전구축 + 신규시장 생성) |
| material-analyzer | 자료·벤치마크 흐름 분석(#9) + 후기 선분석(#7) |
| image-bridge | OpenAI/Gemini 이미지 BYOK(옵션 A 샌드박스 직접호출 우선, B 커넥터 폴백) |
| poster-ad-builder | 포스터/광고 단일 비주얼(1:1·4:5·9:16, 통이미지/후조판) |
| print-creative-builder | 인쇄물 PDF(CMYK·재단 3mm·300dpi, 프리플라이트 전제) |

## 기존 스킬과의 조합(평탄 gil: 체이닝, 실존 검증)
- 후기: gil:commerce-voc-triage / 상품사진: gil:product-photo-brief
- 상세: gil:detail-page-planner → gil:detail-page-copy → gil:detail-page-image / gil:landing-page·product-detail
- 카드뉴스: gil:card-news / SNS: gil:sns-content·copywriting
- 이미지 프롬프트: gil:gpt-image-2-prompt·gemini-3-image-prompt / 폴백: gil:higgsfield-image
- 디자인 토큰: gil:design-system-prep / 인쇄: gil:pdf-writer / 시장규모: gil:market-analyst
- QA: gil:ai-slop-reviewer → gil:humanize-korean → gil:korean-spell-check → gil:commerce-marketing-compliance-kr

## 정책·게이트
- **통합본 단일 유지보수 원칙 확정**: 분리본(29/30-repo) 동결, 통합본 gil만 갱신(§ CLAUDE.md 핵심 원칙 10).
- 버전 전 지점 v1.6.0 → **v1.7.0**(plugin.json ×1 + SKILL.md ×196).
- 게이트 전수 PASS: gil-도메인: 평탄화 0건 · moai 0건 · 끊긴 교차참조 0 · YAML/예약어(claude)/dir==name · zip 슬래시 경로.
- 라이선스: gil-creative = GIL 오리지널(자체 저작물, attribution 불필요).

## 롤백
- `gil-unified-v1.6.0-clean/` (직전 통합본).
