# AGENTS.md

이 저장소를 다루는 모든 AI 에이전트(Claude, ChatGPT, Copilot, Aside 등)가 따라야 하는 규칙입니다.

## 프로젝트
- `index.html`: "RE 측정 판정 보고서 생성기". 단일 HTML 파일.
- 스펙트럼 분석기 이미지를 OpenAI / Claude API로 OCR하고, FCC Part 15 Class B 한계값(보정계수 CF -52 dB 기본)과 비교해 PASS/FAIL을 판정한 뒤 report_template.docx 서식으로 보고서를 생성합니다.

## 브랜치 규칙 (필수)
- `index.html` 등 소스코드를 수정할 때는 항상 새 브랜치를 만들어 반영합니다.
- `main` / `master`에는 직접 커밋하거나 푸시하지 않습니다. (로컬 pre-commit 훅이 차단함)
- 브랜치 이름: `change/<yyyyMMdd-HHmmss>` 또는 `change/<작업-설명>`
- 간편 실행: `.\save-change.ps1 -Message "수정 내용"` (새 브랜치 생성, 커밋, 푸시)
- main으로의 병합은 사용자가 GitHub에서 Pull Request로 직접 승인합니다.

## 보안
- API 키, 토큰, 비밀번호를 코드나 커밋에 넣지 않습니다. API 키는 UI에서 입력받는 방식을 유지합니다.
- 고객 데이터나 측정 이미지 원본은 마스킹 없이 커밋하지 않습니다.

## 작업 방식
- 변경은 작고 명확하게 하고, 커밋 메시지는 무엇을 왜 바꿨는지 한 줄로 적습니다.
- 동작 방식(판정 기준, CF 값 등)을 바꿀 때는 사용자에게 먼저 확인합니다.
- 사용자는 한국어를 사용하므로 설명과 커밋 요약은 한국어를 우선합니다.