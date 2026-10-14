# 2026 AI활용 의성군 서비스 개선 공모제안 경진대회 · 응모 안내

의성군 공고에 따른 경진대회 응모 안내 페이지입니다. 서버 없이 동작하는 정적 사이트입니다.

## 구성

| 경로 | 내용 |
|---|---|
| `index.html` | 안내 페이지 전체 (HTML·CSS·JS 한 파일) |
| `forms/application-form.hwpx` | 붙임1. 제출서류(참가신청서·기획서) 서식 |
| `forms/notice.hwpx` | 공고문 |
| `assets/logo.png` | 의성군 CI |
| `assets/og.png` | 링크 공유 시 미리보기 이미지 (1200×630) |
| `assets/favicon.png`, `assets/apple-touch-icon.png` | 사이트 아이콘 |
| `404.html`, `robots.txt`, `.nojekyll` | GitHub Pages 보조 파일 |

## 운영 설정

`index.html` 하단 `CONFIG`에서 바꿉니다.

- `closeAt`: 접수 마감(기본 2026-10-31T00:00 KST = 10.30.(금) 24:00). 마감이 지나면 접수 버튼이 자동으로 닫히고 안내 문구가 바뀝니다. `finalsAt`, `dayAt`, `doneAt`도 같은 방식입니다.
- `statusOverride`: `'open' | 'closed' | 'finals' | 'done'` 중 하나를 넣으면 날짜와 관계없이 그 상태로 고정됩니다.
- `forms`: 서식·공고문 파일 경로. 파일을 바꿀 때는 `forms/` 안의 파일만 교체하면 됩니다. 내려받을 때 표시되는 한글 파일명은 각 링크의 `download` 속성에 있습니다.

## 표기 규칙

- 라벨·제목의 복합명사는 붙여 씁니다(응모안내, 공모분야, 제출서류, 접수마감 등).
- 고정 구와 숫자+단위는 줄 중간에서 끊기지 않도록 `&nbsp;`로 묶습니다.
- 날짜는 `년.월.일.` 형식으로 일 뒤에도 마침표를 씁니다(예: 2026.10.30.(금)).

## 배포 (GitHub Pages + 구매 도메인)

1. 이 폴더를 저장소 루트로 GitHub에 올립니다. 브랜치 `main`.
2. 저장소 Settings → Pages → Source: `Deploy from a branch`, Branch: `main` / `/ (root)`.
3. Custom domain에 구매한 도메인을 입력하고 저장하면 `CNAME` 파일이 생깁니다.
4. 도메인 등록업체 DNS에 아래를 추가합니다.
   - 루트 도메인(example.kr): A 레코드 `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www`: CNAME 레코드 → `<GitHub 계정>.github.io`
5. DNS 반영(수 분~수 시간) 후 Pages 화면에서 `Enforce HTTPS`를 켭니다.
6. 이후 수정은 `index.html`을 고쳐 커밋·푸시하면 1분 안에 반영됩니다.
