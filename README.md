# AutoWeb 프로젝트 기록

이 저장소는 ChatGPT와 GitHub Actions, Vercel을 연동해 **자연어로 웹사이트를 수정·배포**하는 완전 자동화 실험 프로젝트입니다.

---

## 📦 현재 구성
- **배포 주소:** [https://auto-web-lyart.vercel.app](https://auto-web-lyart.vercel.app)
- **자동화 흐름:** ChatGPT → GitHub Connector → Pull Request 생성 → CI 체크 → 자동 머지 → Vercel 자동 배포
- **주요 워크플로**
  - `.github/workflows/ci.yml` → PR 체크
  - `.github/workflows/automerge.yml` → 자동 머지

---

## 🧩 최근 작업 요약
| 날짜 | 내용 | 커밋/PR |
|------|-------|----------|
| 2025-10-28 | `index.html` 복원 및 "수정완료 ✅" 표시 추가 | [d62ce52](https://github.com/quokkstudio/autoWeb/commit/d62ce52cf19ffd54bbdc400a335fbcad67eff80d) |
| 2025-10-28 | `feat/scaffold` 브랜치 생성, 정적 사이트 기본 구조 구성 | [PR #4](https://github.com/quokkstudio/autoWeb/pull/4) |
| 2025-10-28 | `fix/automerge-github-script` PR 생성 (peter-evans/auto-merge 대체) | [PR #5](https://github.com/quokkstudio/autoWeb/pull/5) |
| 2025-10-29 | `quokk/html, css, js` 폴더 생성 및 레이아웃 스캐폴딩 | [688c7e7](https://github.com/quokkstudio/autoWeb/commit/688c7e7613578ec67bf82d6e384d02cbd0f72dff) |

---

## 🖼️ 피그마 연동 계획
디자인은 아래 Figma 파일을 기반으로 합니다.

👉 [Convil 디자인 파일 열기](https://www.figma.com/design/gleEyaoYG6MdWTj07hoUFg/convil_design?t=yfv1Cj5sRR4SXkit-0)

이후 단계에서 ChatGPT가 Figma API를 통해 디자인 요소를 읽고, 해당 스타일/레이아웃을 코드(`HTML`, `CSS`, `React`)로 자동 변환할 예정입니다.

---

## 🚀 다음 단계
- [ ] `convil_design` 피그마 파일의 주요 프레임 구조 읽기
- [ ] Figma → 코드 자동 변환 모듈 추가
- [ ] `autoWeb` 배포 루프에 Figma 기반 UI 반영

---

> ⚙️ **참고:** 이 README는 ChatGPT가 자동으로 작성했습니다.
> 새로운 세션에서 프로젝트를 이어가려면 이 문서를 참조하세요.

---

✅ 수정완료
