# 2026 INVENTION LAB

서울시교육청 융합과학교육원 「2026 발명(심화) 과정」 학생 프로젝트 전시관.

## 1. GitHub Pages에 바로 배포하기

권장 저장소 이름: **`invention-lab-2026`**

1. GitHub에서 새 **Public** 저장소를 만듭니다. (GitHub 무료 계정에서 Pages를 쓸 경우 Public 저장소를 권장합니다.)
2. 이 ZIP 파일을 **압축 해제**하세요.
3. 압축을 푼 폴더의 `index.html`과 `assets` 폴더를 **함께**, GitHub 저장소의 **맨 위(root)** 위치에 올립니다. ZIP 파일 자체를 업로드하는 것이 아닙니다.
4. GitHub **Settings → Pages → Build and deployment**에서 **Deploy from a branch**, `main`, `/(root)`를 선택하고 저장합니다.
5. 배포되면 Pages에 표시되는 링크로 접속합니다. 주소 형태는 대개 `https://사용자명.github.io/invention-lab-2026/`입니다.

폴더 구조:

```text
invention-lab-2026/
├── index.html
├── assets/
│   ├── watering.webp
│   ├── magnet.webp
│   └── medicine.webp
└── README.md
```

`index.html`을 더블클릭하면 인터넷 연결 없이도 전시관 화면과 회전 기능을 볼 수 있습니다(팀별 Google Sites 연결은 인터넷이 필요합니다).

## 2. 세 팀의 홈페이지 주소

- **TEAM 01 자동 물주기**: https://sites.google.com/view/vdwzvwtdgg/
- **TEAM 02 자석 위치 제어**: https://sites.google.com/view/chickenpizzahamberger/
- **TEAM 03 복약 알림 약통**: https://sites.google.com/sonline20.sen.go.kr/nova20261015/%ED%99%88

### 주소 변경

`index.html`을 텍스트 편집기로 열고 아래 부분을 찾으세요.

```javascript
const PROJECTS = [
  {id:1, ..., websiteUrl:'https://sites.google.com/view/vdwzvwtdgg/'},
  {id:2, ..., websiteUrl:'https://sites.google.com/view/chickenpizzahamberger/'},
  {id:3, ..., websiteUrl:'https://sites.google.com/sonline20.sen.go.kr/nova20261015/%ED%99%88'}
];
```

각 팀의 `websiteUrl`만 바꾸면 3D 슬라이드, 작품 카드, 상세 소개에서 동일하게 반영됩니다.

팀 추가는 `PROJECTS` 배열에 새 객체를 추가해 진행할 수 있지만 **현재 3D 캐러셀의 좌·중앙·우 배치는 정확히 3개 작품을 기준으로 설계**되어 있습니다. 4팀 이상으로 확장하려면 캐러셀의 위치 계산 방식도 수정해야 합니다. (프로젝트 목록, 검색, 분야 필터는 데이터에 따라 자동으로 갱신됩니다.)

### 글이나 이미지 변경

- 제목 변경: 각 객체의 `title`
- 핵심 소개: `summary`
- 이미지 파일: `assets/` 안의 WebP 파일을 교체하고, 필요하면 `image` 경로를 수정
- 상세 내용: `components`, `steps`, `tags`
- 프로젝트 정보 전체: `index.html` 아래쪽 `PROJECTS` 배열

## 3. 인터랙션

- **PC**: 옆 카드를 마우스로 가리키면 그 카드가 3D 회전하며 앞으로 옵니다.
- **모바일**: 카드를 터치하거나 좌우로 밀면 회전합니다.
- **공통**: 이전/다음 화살표, 슬라이드 점 표시, 방향키를 사용할 수 있습니다.
- 동그란 ↻ 버튼으로 자동 회전을 켜거나 끌 수 있습니다. 기본은 꺼짐입니다.
- ‘작품 자세히’를 누르면 부품 및 제작 단계가 나오는 설명창이 열립니다.
- ‘팀 홈페이지 방문’을 누르면 실제 팀 Google Sites가 새 탭에서 열립니다.

## 4. 구성 안내

- 설치, 빌드, Node.js, 데이터베이스, 별도 서버가 필요 없습니다.
- HTML / CSS / JavaScript만 사용합니다.
- 외부 이미지 서버나 폰트 없이도 동작합니다.
- 이미지 3장은 동일한 파스텔 일러스트 톤으로 제작한 콘셉트 그림이며, 실물 완성품 사진이 아닙니다.
- **작품명은 처음 제공된 자료를 토대로 한 가칭**이며 실제 팀 발표 제목으로 수정할 수 있습니다.
- 팀 홈페이지 공개 범위는 Google Sites의 공유 설정에 따라 다릅니다. 외부에서 보려면 해당 사이트에 방문 권한이 있어야 합니다.

## 5. 한 파일만 올리는 대안

별도로 전달된 **단일 파일용 `index.html`**에는 이미지가 파일 내부에 포함되어 있습니다. 그 파일만 GitHub 저장소 맨 위에 올리면 되며 `assets/` 폴더가 필요하지 않습니다. 단, 이미지 교체는 분리형 ZIP 버전이 더 쉽습니다.
