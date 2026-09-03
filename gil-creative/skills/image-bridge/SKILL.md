---
name: image-bridge
description: |
  [한·UZ 듀얼 · gil-creative] 크리에이티브 설계의 이미지 프롬프트를 실제 이미지로 생성하는 외부 API 브리지입니다. OpenAI(gpt-image 계열)와 Google Gemini(Imagen/Gemini Image) 최신 모델을 BYOK(사용자 키)로 호출합니다. 비라틴·다국어는 배경만 생성하고 카피는 후조판합니다. 이미지 생성만 외부이고, 나머지 텍스트 지능은 Claude가 직접 수행합니다.
  다음과 같은 요청 시 사용하세요:
  - "이 프롬프트로 이미지 생성해줘"
  - "OpenAI/Gemini로 히어로 이미지 만들어줘"
  - "배경 이미지만 생성 (후조판용)"
  - "포스터 비주얼 렌더"
  - "rasm yaratish" (이미지 생성, UZ)
  프롬프트 설계는 gil-creative:gpt-image-2-prompt·gil-creative:gemini-3-image-prompt와, 커넥터 폴백은 gil-creative:higgsfield-image와 조합합니다. BYOK 키는 환경변수/세션에만 두고 저장·메모리 기록하지 않습니다.
version: "2.2.1"
---

# 이미지 브리지 (Image Bridge) — BYOK

> **역할** gil-creative:creative-architect가 만든 이미지 프롬프트를 OpenAI/Gemini 최신 이미지 모델로 렌더한다. **이미지 생성만 외부**, BYOK.
> **보안 원칙** 사용자 API 키는 **환경변수/세션에만** 둔다. 파일·메모리에 저장하지 않고, 로그·산출물에 노출하지 않는다.

---

## 1. 제공자·모델
- **OpenAI**: 최신 gpt-image 계열(구현 시점 최신 버전). 프롬프트 = gil-creative:gpt-image-2-prompt 산출.
- **Google Gemini**: Imagen / Gemini Image 계열. 프롬프트 = gil-creative:gemini-3-image-prompt 산출.
- **제공자 토글**: 사용자가 `--provider openai|gemini` 선택. 기본 = openai.

---

## 2. 실행 옵션 (Cowork 제약 대응)

| 옵션 | 설명 | 우선순위 |
|---|---|---|
| **A. 샌드박스 직접 호출** | 스킬 스크립트가 API 직접 호출 (BYOK) | **Phase 1 우선** (네트워크 허용 검증 후) |
| B. 커넥터 경유 | `gil-creative:higgsfield-image` 등 커넥터로 생성 | A 실패 시 폴백 |
| C. 서버 프록시 | 자체 서버가 키 받아 프록시 | Phase 2 |

> **동작**: A를 먼저 시도(`scripts/generate_image.py`). 샌드박스에서 네트워크가 막히면 즉시 B(커넥터)로 폴백하고 사용자에게 안내한다.

---

## 3. 파라미터

| 파라미터 | 값 |
|---|---|
| `--provider` | openai \| gemini |
| `--size` / `--aspect` | 1:1 · 4:5 · 9:16 · 16:9 |
| `--mode` | flat(통이미지) \| overlay(배경만, 후조판) |
| `--prompt` | 구조 + 레이아웃 규칙 + 시장 톤 오버레이 |
| `--n` | 시안 수 |

- **비라틴·다국어**: `--mode overlay`로 **배경만 생성**. 카피는 빌더가 코드/디자인으로 후조판(§ gil-creative:creative-architect 방법론 #10). CIS 기본 overlay.

---

## 4. BYOK 설정
```
# 환경변수 (세션 한정, 저장 금지)
export OPENAI_API_KEY="sk-..."
export GEMINI_API_KEY="..."
```
- 키가 없으면 스킬이 입력을 요청하고, 세션 종료 시 폐기. 메모리 파일에 절대 기록하지 않는다(민감정보 규칙).

---

## 5. 스크립트
- `scripts/generate_image.py` — provider 토글로 OpenAI/Gemini 호출, size/aspect/mode 지원, 결과를 outputs 폴더에 저장. 네트워크 차단 시 커넥터 폴백 안내를 stderr로 반환.
- 사용: `python3 scripts/generate_image.py --provider openai --aspect 4:5 --mode overlay --prompt "..." --out hero_bg.png`

---

## 6. 체이닝
| 목적 | 스킬 |
|---|---|
| OpenAI 프롬프트 설계 | `gil-creative:gpt-image-2-prompt` |
| Gemini 프롬프트 설계 | `gil-creative:gemini-3-image-prompt` |
| 커넥터 폴백(옵션 B) | `gil-creative:higgsfield-image` |
| 설계 입력 | `gil-creative:creative-architect` |
| 포맷 합성 | `gil-creative:poster-ad-builder`·`gil-commerce:detail-page-image`·`gil-creative:print-creative-builder` |

> UZ/CIS 후조판·채널 규격은 `references/uz-image-bridge.md`.
