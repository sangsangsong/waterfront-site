# Waterfront Equity — One-Page Site

Mid-market private equity firm의 단일 페이지 소개 사이트입니다. 빌드 도구나 의존성 없이 순수 HTML/CSS/JS로 작성되어 GitHub Pages에 바로 호스팅할 수 있습니다.

## 구조

```
.
├── index.html              # 전체 페이지 (단일 스크롤)
├── .nojekyll               # GitHub Pages의 Jekyll 처리 비활성화
└── assets/
    ├── css/styles.css      # 스타일 (명함 기반 팔레트)
    ├── js/main.js          # 스크롤 헤더 · 모바일 메뉴 · 리빌 애니메이션
    └── images/
        ├── hero-yacht.jpg          # 데스크탑 hero 배경
        ├── hero-yacht-mobile.jpg   # 모바일 hero 배경
        └── spinnaker.jpg           # Approach 섹션 이미지
```

## GitHub Pages 배포

1. GitHub에서 새 repository 생성 (예: `waterfront-site`)
2. 이 폴더의 파일 전체를 push
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<사용자명>/waterfront-site.git
   git push -u origin main
   ```
3. Repository → **Settings → Pages**
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)` 선택 후 저장
4. 1~2분 후 `https://<사용자명>.github.io/waterfront-site/` 에서 확인

## 커스텀 도메인 (waterfronteq.com) 연결 — 선택

1. `assets` 와 같은 위치(루트)에 `CNAME` 파일을 만들고 한 줄로 도메인 입력:
   ```
   www.waterfronteq.com
   ```
2. GoDaddy DNS에서:
   - `www` → CNAME → `<사용자명>.github.io`
   - 루트 도메인(`@`)을 쓰려면 A 레코드 4개를 GitHub Pages IP로 지정
     (`185.199.108.153`, `.109.153`, `.110.153`, `.111.153`)
3. Settings → Pages → Custom domain 에 도메인 입력 후 **Enforce HTTPS** 체크

> 참고: GitHub Pages 공식 IP는 변경될 수 있으므로 배포 시점에 GitHub 문서에서 최신 값을 확인하는 것을 권장합니다.

## 수정 가이드

- **문구**: `index.html` 내 각 섹션 텍스트를 직접 편집
- **색상**: `styles.css` 상단 `:root`의 CSS 변수 (`--navy`, `--gold`, `--cream` 등)
- **이미지 교체**: `assets/images/`의 파일을 같은 이름으로 교체하거나, HTML/CSS의 경로 수정

## 참고: 콘텐츠에 대한 주의

본문 문구(투자 기준, 회사 소개 등)는 일반적인 mid-market PE 사이트의 표준 구성을 바탕으로 작성한 **초안**입니다. 실제 펀드 규모, 트랙 레코드, 포트폴리오, 규제 표기(예: 유한책임회사 관련 법적 고지) 등은 사실 확인 후 보강하시길 권합니다. 특히 대외 신뢰성이 중요한 업종 특성상, 검증되지 않은 수치나 실적을 넣지 않은 것은 의도된 선택입니다.
