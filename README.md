# hspark.github.io — 개인 연구 홈페이지

정적 HTML 3쪽. 빌드 도구·의존성 없음. GitHub Pages에 그대로 올라갑니다.

```
index.html        About (소개·연구관심·연락처)
research.html     Research (주제 3축 + 방법 + 데이터)
publications.html Publications (게재·투고중·워킹페이퍼)
style.css         공용 스타일 (라이트/다크 자동)
photo.jpg         ← 넣어야 함
cv.pdf            ← 넣어야 함
```

---

## 배포 (최초 1회)

### 1. 저장소 만들기

GitHub에서 새 저장소를 만듭니다. **이름은 반드시 `<사용자명>.github.io`** 여야 주소가 `https://<사용자명>.github.io` 로 깔끔하게 나옵니다.

- Public
- README·.gitignore·license **전부 체크 해제** (빈 저장소로)

### 2. 올리기

이 폴더에서:

```bash
cd ~/Documents/hspark-website && git init -b main && git add -A && git commit -m "Initial site"
```

원격 연결 후 push (`<사용자명>` 교체):

```bash
cd ~/Documents/hspark-website && git remote add origin https://github.com/<사용자명>/<사용자명>.github.io.git && git push -u origin main
```

push 할 때 GitHub 로그인을 물으면 브라우저 인증을 따르면 됩니다. 비밀번호 대신 토큰을 요구하면
Settings → Developer settings → Personal access tokens 에서 발급합니다.

### 3. Pages 켜기

저장소 → **Settings → Pages** → Source 를 **Deploy from a branch**, Branch 를 **main / (root)** → Save.

1–2분 뒤 `https://<사용자명>.github.io` 에서 열립니다.

---

## 이후 수정

파일 고치고:

```bash
cd ~/Documents/hspark-website && git add -A && git commit -m "Update" && git push
```

---

## 로컬 미리보기

```bash
cd ~/Documents/hspark-website && python3 -m http.server 8000
```

→ http://localhost:8000

---

## 채워야 할 자리 (REPLACE_ME / TODO)

| 위치 | 내용 |
|---|---|
| 전체 3쪽 nav | Google Scholar 프로필 ID |
| `index.html` | ORCID |
| `index.html` | `photo.jpg` — 정면 인물사진 (정사각 권장, 600×600 이상) |
| 전체 3쪽 nav | `cv.pdf` — CV PDF 파일명을 `cv.pdf` 로 저장해 이 폴더에 |
| `publications.html` | **JCPP 2025, 67(5)** — 저자 목록·제목 미확보 |

## 서지 확인 필요 (게시 전)

MEMORY 기록 기준으로 CV 원본의 오류 4건을 이미 반영했습니다. **게시 전 게재본으로 최종 확인하십시오.**

| 항목 | CV 원본 | 이 사이트에 반영한 값 | 상태 |
|---|---|---|---|
| SSM (우울→CVD) | 313 | **318** | MEMORY 정정 반영 |
| SSM (불안정고용) | 329, 2023 | **341, 2024** | MEMORY 정정 반영 |
| AJCJ 3저자 | Fong, E. | **Kim, T.** | MEMORY 정정 반영 |
| PRPR | 45(2), 2025 | **45(2), 2026** | MEMORY 정정 반영 — 단 인수인계 문서는 45(1), 2025.12 로 기록. **불일치, 확인 필요** |
| J. of Adolescence | 101 | **97(3)** | 인수인계 문서 기준. **불일치, 확인 필요** |

## 선택 사항

- **커스텀 도메인**: 도메인을 사면(연 1–2만원) Settings → Pages → Custom domain 에서 연결. 무료로 쓰려면 불필요.
- **국문 페이지**: 현재 영문 전용. 필요하면 `ko/` 폴더로 추가.
- **논문 목록 자동화**: 지금은 HTML 직접 입력. 편수가 늘면 Jekyll(al-folio) + Zotero BibTeX 연동으로 전환 가능.
