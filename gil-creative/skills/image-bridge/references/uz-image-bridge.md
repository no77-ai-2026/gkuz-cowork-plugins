# UZ/CIS 듀얼 컨텍스트 — image-bridge

> 한국 표준 + 우즈베키스탄/CIS. 이미지 생성·후조판.

## 후조판 기본 (비라틴)
- 키릴(RU)·우즈벡(UZ) 텍스트는 이미지 모델 오타 리스크가 커서 `--mode overlay`(배경만 생성) 기본.
- 카피는 빌더가 코드/디자인으로 후조판 → 언어 전환·문구 수정·인쇄 재사용 유리.

## 채널 규격 (UZ)
- Uzum Market·Yandex·OLX·Telegram 이미지 규격이 다름 → aspect를 채널에 맞춰 지정(1:1·4:5·9:16).
- 결제·인증 아이콘(Payme·Click·적합성 인증)은 이미지에 굽지 말고 후조판 배지 슬롯으로.

## 금기색·상징
- gil-creative:market-profile-engine의 문화 차원에서 금기색·상징을 받아 프롬프트에서 제외.

## BYOK
- OPENAI_API_KEY / GEMINI_API_KEY는 세션 환경변수로만. 저장·메모리 기록 금지.
- 샌드박스 네트워크 차단 시 gil-creative:higgsfield-image 커넥터로 폴백.
