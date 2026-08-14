# GIL — Claude Cowork Plugins (한·UZ 듀얼)

![Version](https://img.shields.io/badge/version-2.2.0-blue) ![Plugins](https://img.shields.io/badge/plugins-3-green) ![Skills](https://img.shields.io/badge/skills-298-orange)

한국 표준 + 우즈베키스탄 듀얼 컨텍스트의 Claude Cowork 플러그인 마켓플레이스입니다.
"GIL — 한국과 중앙아시아를 잇는 길"

## 번들 구성

| 번들 | 스킬 | 버전 | 내용 |
|---|---|---|---|
| **gil** (코어) | 148 | 2.2.0 | 전략·컨설팅·문제해결(PSA)·검증형 리서치·오피스 문서(Word/PPT/Excel/한글/PDF)·데이터/공공데이터·법무·재무/세무·HR·CS·교육·연구·특허·ODA·생산성·커리어 + 에이전트 16 + MCP 6종 |
| gil-creative | 96 | 2.1.0 | 마케팅·콘텐츠·카피·디자인·광고 크리에이티브·이미지/영상/오디오·스토리 IP(웹툰·웹소설·시나리오)·출판 |
| gil-commerce | 54 | 2.1.0 | 스마트스토어·쿠팡·자사몰·UZ 채널(Uzum·OLX·Telegram·Yandex) 셀러 운영·상세페이지·광고 최적화·소상공인 루틴 |

## 설치

**방법 1 — 마켓플레이스 추가 (Claude Code)**

```
/plugin marketplace add no77-ai-2026/gil-cowork-plugins
/plugin install gil@gil-plugins
```

**방법 2 — 파일 업로드 (Claude 데스크톱/Cowork)**

각 번들 폴더를 zip으로 압축(`.plugin` 확장자, 내용물이 zip 루트에 오도록)한 뒤, Claude 데스크톱 앱 → 설정 → 플러그인 → 업로드.

## v2.2.0 하이라이트

- **problem-solving** (신규) — PSA 문제 구조화: SCQ → 이슈화(3-Test: Fact/Fork/Action) → 로직트리 5유형 → 가설 QDT → Work Plan
- **research-verify** (신규) — 검증형 리서치: 출처 병기·[미검증]/[추정] 태그 → 3중 검증(팩트·출처·논리) → Red 반론 → 조건부 결론
- 기존 스킬 8종·에이전트 2종에 유기적 연동 라우팅 추가

상세 이력: `gil/CHANGELOG-v2.2.0.md` 및 각 번들 CHANGELOG.

## 라이선스

Apache-2.0 — 모태 [modu-ai/moai-cowork](https://github.com/modu-ai/moai-cowork) 차용·확장. 재배포 시 `LICENSE`·`NOTICE.md`를 함께 유지해 주세요. 제3자 구성요소는 각 라이선스 우선 (NOTICE.md 참조).
