# eatlho_home

잇냉(eatlho) 앱 공식 소개 + 법적 문서 정적 웹사이트.

- 기술 스택: Astro (minimal), 순수 CSS, TypeScript
- 배포: GitHub Pages (커스텀 도메인: eatlho.com)

## 로컬 실행

```bash
npm install
npm run dev
```

브라우저에서 `http://localhost:4321` 접속.

## 빌드

```bash
npm run build
```

빌드 결과물은 `dist/` 디렉토리에 생성됩니다.

## 배포 방법

`main` 브랜치에 push하면 GitHub Actions(`.github/workflows/deploy.yml`)가 자동으로 빌드 후 GitHub Pages에 배포합니다.

### 최초 배포 시 설정 순서

1. GitHub 리포지토리 생성 및 push
2. 리포 설정 > Pages > Source를 **GitHub Actions**로 변경
3. 리포 설정 > Pages > Custom domain에 `eatlho.com` 입력
4. 도메인 DNS 설정에서 CNAME 레코드를 `<username>.github.io`로 지정
5. `public/CNAME` 파일이 이미 `eatlho.com`으로 설정되어 있음

## TODO — 정책 플레이스홀더 교체

법적 문서(`src/pages/terms.astro`, `src/pages/privacy.astro`) 내 아래 항목을 실제 정보로 교체 후 배포:

- `[운영자명]` — 서비스 운영 법인명 또는 개인 상호
- `[대표자명]` — (약관에 추가 시)
- `[사업자 주소]` — (약관에 추가 시)
- `[사업자등록번호]` — (약관에 추가 시)
- `[개인정보 보호책임자명]` — 개인정보처리방침 9조
- `[개인정보 보호 담당 이메일]` — 개인정보처리방침 9조
- `[시행일자]` — 이용약관 부칙 및 개인정보처리방침 시행일 (예: 2026년 X월 X일)
- `contact@eatlho.com` — Footer 문의 이메일 (`src/components/Footer.astro`)

## TODO — 스토어 출시 후

- `src/pages/index.astro` 내 CTA 섹션(주석 표기된 부분)에 Google Play / App Store 배지 링크로 교체
