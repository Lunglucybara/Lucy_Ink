# 루시잉크 v0.6 · 장식 아이콘 30종 추가

퀵메뉴·썸네일 등에서 고를 수 있는 벡터 아이콘을 70종 → **100종**으로 늘렸습니다.
이번에 추가된 30종은 전부 기능 아이콘이 아니라, 순수하게 **디자인적·장식적인 컨셉**으로만 구성했습니다.

## 1. 신규 아이콘 30종

기존 `mood`(장식) 카테고리에 이어서 추가되며, 필터 화면의 "장식" 탭에서 함께 보입니다.

**스테이셔너리 · 필기 데스크**
압화(pressed-flower) · 봉랍 인장(wax-seal-stamp) · 바늘과 실(needle-thread) ·
실타래(spool-thread) · 붓과 팔레트(paintbrush-palette) · 빈티지 타자기(vintage-typewriter) ·
빈티지 가위(antique-scissors) · 책갈피 리본(bookmark-ribbon)

**빈티지 소품 · 골동품**
회중시계(pocket-watch) · 나침반(vintage-compass) · 보물상자(treasure-chest) ·
손거울(hand-mirror) · 향수병(perfume-vial) · 레이스 도일리(lace-doily)

**환상 · 신비 모티프**
별자리 지도(constellation-map) · 수정구(crystal-ball) · 타로카드(tarot-card) ·
스노우글로브(snow-globe) · 오르골(music-box) · 랜턴(lantern-glow)

**보태니컬 · 자연**
단풍잎(maple-leaf) · 드라이플라워 장미(dried-rose) · 나비 표본(butterfly-specimen)

**패션 · 주얼리**
리본 매듭(ribbon-bow) · 브로치(jewelry-brooch) · 로켓 목걸이(locket-heart) · 쥘부채(folding-fan)

**아늑함 · 티타임**
김 나는 찻잔(teacup-steam) · 새장(birdcage-ornament) · 선물상자(gift-ribbon-box)

## 2. 디자인 원칙

- 기존 70종과 완전히 동일한 "Lucid Drop" 젬·스테이셔너리 톤으로 제작 — 새 컬러를 하드코딩하지 않고
  기존 `--li-icon-*` 런타임 토큰(21종)만 사용해, 10개 컬러 테마 + 라이트/다크 어디서든 자동으로 톤이 맞습니다.
- 배경 셸은 라운드 사각형·원형·스캘럽 사각형 세 가지를 아이콘 성격에 맞게 번갈아 사용해
  기존 70종과 나란히 놓아도 단조롭지 않도록 구성했습니다.
- 모든 신규 아이콘은 `category: "mood"`(장식)로 등록해, 필터 UI 변경 없이 기존 "장식" 탭에 자연 편입됩니다.

## 보존 원칙 (Additive-only)

- 기존 70종 아이콘의 `id`·`label`·SVG·CSS 변수·구조는 전혀 건드리지 않았습니다 — 배열 끝에 30종만 추가.
- `quickmenu-icon-library.js` 상단 버전 주석만 `v66.6` → `v66.7`로 갱신(아이콘 총량 100종 명시).
- `index.html`의 아이콘 팔레트 주석에는 갱신 노트 한 줄만 **추가**했고, 기존 문구는 그대로 두었습니다.
- 퀵메뉴/프로젝트 라이브러리 카드 렌더 로직(`quickMenuLibraryIconMarkup`, `sanitizeQuickMenuSvg` 등)은 수정하지 않았습니다 — 신규 아이콘도 기존 로직 그대로 통과합니다.

## 검증

- Node로 `quickmenu-icon-library.js` 구문·무결성 검사: 아이콘 100개, id 중복 없음, svg 누락 없음.
- 신규 30종 전체 XML well-formed 검사 통과.
- Playwright headless Chromium, 뷰포트 412×915 · dpr2 기준으로 4개 컬러 테마 조합(light/pink, dark/navy, light/dgreen, dark/gold) 렌더 스크린샷 확인 — 실제 앱의 `index.html` 스타일 시트를 그대로 불러와 검증했습니다.

## 배포

- Service Worker 캐시 키: `luci-ink-v0.5-diary-adjusted` → `luci-ink-v0.6-diary-icons30`
