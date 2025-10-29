# AutoWeb 자동화 운영 가이드

이 문서는 자연어 요청으로 코드 수정 → PR → 자동 배포까지 이어지는 루프를 설명합니다. 또한 ZIP 업로드 워크플로 사용법도 포함합니다.

## 파이프라인 개요
1) 요청: "헤더 로고 교체해줘", "convil.zip 반영해줘" 등
2) 작업: ChatGPT가 브랜치/PR 생성하거나, `drop` 브랜치 ZIP 업로드 워크플로 실행
3) 검증: CI 체크 통과 (`ci.yml`)
4) 자동 머지: `automerge.yml`
5) 배포: Vercel가 `main` 변경 감지 → 자동 배포

## ZIP 업로드 워크플로
- 워크플로: `.github/workflows/unzip-upload.yml`
- 트리거: `drop` 브랜치에 `*.zip` push
- 동작: ZIP을 `import/zip-<run_id>` 브랜치에 전개 → PR 생성 → main 머지
- 안전장치: 기존 파일은 유지. `index.html` 충돌 시 `index_convil.html`로 저장

## 사용 예시
- Figma to Code Export 반영: `convil.zip`을 `drop`에 업로드하면 자동 반영됩니다.
- 기본 진입점 교체: `index_convil.html`을 기본 `index.html`로 바꾸고 싶다면 추가 요청만 하면 됩니다.

## 요청 템플릿
- "drop에 convil.zip 올렸어. 루트에 그대로 반영해줘. 기존 파일 유지하고, index 충돌 시 index_convil.html로."
- "index_convil.html을 기본 진입점으로 교체 PR 만들어서 배포까지."

## 트러블슈팅
- 워크플로가 안 보이면 PR `chore/add-unzip-upload-ci` 상태 확인
- 배포 확인: Vercel Deployments 또는 `https://auto-web-lyart.vercel.app/index_convil.html`
