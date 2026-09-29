# 동네자판기 홈페이지 — 작업 인수인계 (새 채팅용)

새 채팅에서 이 저장소(`dkfmaqqhh-cyber/dongne-vending`)를 연결하면 이 문서부터 읽고 이어서 작업한다.

## 한눈에 보기
- 사이트: https://dkfmaqqhh-cyber.github.io/dongne-vending/
- 정보 글 목록: https://dkfmaqqhh-cyber.github.io/dongne-vending/posts/
- 글 관리자(Sveltia CMS): https://dkfmaqqhh-cyber.github.io/dongne-vending/admin/  (GitHub fine-grained 토큰, dongne-vending 저장소 Contents: Read and write)
- 배포: GitHub Pages (main 브랜치 / root, Jekyll 자동 빌드). 푸시 후 1~3분 뒤 반영
- 빌드 확인: `curl -s "https://api.github.com/repos/dkfmaqqhh-cyber/dongne-vending/actions/runs?per_page=1"`
- 같은 계정의 다른 저장소 `spacereborn-site` = '오늘의 철거'(onulcheolgeo.kr) 사이트. 섞지 말 것.

## 연락·상담 링크 (전부 반영됨)
- 전화: 010-7990-2378 (`tel:01079902378`)
- 네이버폼(무료 견적 신청): https://naver.me/GxrdxD4F
- 카카오 오픈채팅(실시간 채팅 상담): https://open.kakao.com/o/sdyUEOPi

## 파일 구조
- `index.html` : 메인 한 페이지 (CSS·JS 인라인, 이미지는 `images/`). 수정 시 기존 레이아웃 유지, `</style>` 앞에 "NN차:" 주석 달아 CSS 덧붙이는 방식으로 작업해 옴
- `_posts/*.md` : 정보 글 (front matter: title, date(날짜만), tag, cover(' / '로 줄바꿈), color(brown|orange|olive|navy|teal|red), thumbnail, description, summary(선택: 글 위 '핵심 요약' 박스), faq(선택: q/a 목록 → 본문 아래 FAQ + FAQPage JSON-LD))
- 글 URL은 파일명 기준 `/posts/<slug>/` (예: /posts/rent-vs-lease/). 글 안 내부 링크는 `{{ '/posts/slug/' | relative_url }}` 형식
- `posts/index.html` : 전체 글 목록 / `_layouts/post.html` : 글 페이지(하단 상담 버튼 3개 + 다른 글 3개)
- `_layouts/base.html`, `_includes/card.html`, `assets/post.css` : 글 페이지 공통 틀
- `posts.json` : 메인 '정보' 섹션(#info)이 최신 6개를 fetch 해서 카드로 표시
- `admin/index.html`, `admin/config.yml` : Sveltia CMS (날짜는 date-only로 저장하도록 설정)
- `_config.yml` : baseurl `/dongne-vending`, timezone Asia/Seoul, `future: true`, jekyll-sitemap. 전용 도메인 연결 시 baseurl "" + CNAME 추가
- `robots.txt` : /admin/ 제외, sitemap 링크

## 메인 페이지 섹션 순서 (id)
헤더 메뉴: 자판기종류(#types) · 설치장소·사례(#place) · 정보(#info)  — 모바일에서도 표시, '무료 상담' 헤더 버튼은 삭제함
1. 메인(hero2): 왼쪽 사진 + 오른쪽 브라운 패널(아이콘 타일 4개, 무료 상담 신청→#contact, 설치사례 보기)
2. 가능 상품 목록(#types)
3. 운영의 차이(ops, 진한 브라운, 주간 매출 '예시' 그래프)
4. 자판기 종류 카드(#machines): 스마트/확장형/냉장·냉동 쇼케이스/굿즈&담배. 스마트·쇼케이스는 '핵심 기능' 4개, 쇼케이스는 사진 2장 자동 슬라이드. 모바일은 선택 시 카드로 자동 스크롤
5. 불편했던 기존 방식 vs 스마트 솔루션 이미지
6. 배출 방식 이미지
7. 설치 장소(#place) — 모바일 2열
8. 설치사례(#case) 16곳 — 4개 표시 + '더보기'로 펼침 / 설치 후기 4개 가로 자동 슬라이드
9. 자판기 설치·운영 정보(#info) — posts.json 카드 6개 + 전체 보기
10. 무료 상담(#contact, 상담 가이드형): 실시간 채팅(흰 배경+오렌지 테두리, 95차) / 빠른 전화 연결(흰 배경+브라운 테두리) / 무료 견적 신청(오렌지) 3버튼. 버튼 아래 전화번호 안내 문구(cg-note)는 삭제함
11. 설치 진행 과정(세로 흐름) / FAQ / 푸터 / 모바일 하단 고정바(전화·카톡·상담신청)

## 디자인 기준
- 톤: 크림·샌드 배경 그라데이션 + 진한 브라운(#3b2a20) + 오렌지(#ff5b14) 강조
- 글씨체: 나눔고딕(Nanum Gothic), 작은 글씨는 굵기 400~700
- 로고: images/img_02_... (주황 자판기 + '동네자판기'), 파비콘 img_01_...
- PC/모바일(390·360·320px) 모두 가로 스크롤 없게 확인하며 작업

## 사용자 선호·주의
- 답변은 한국어, 근거 없는 내용은 "잘 모르겠습니다/추측입니다"로 구분, 사실은 답변 끝에 정리
- 광고·홍보성 문구 배제, 정보성·후기성 글(SEO+AEO+GEO 통합형)
- 지어낸 후기·수치를 실제처럼 쓰지 않는다. 현재 설치 후기 4개(김**, 박**, 이**, 최**)는 실제 후기인지 사용자 확인 필요
- 확인 필요 항목: '방문 접수' 표현, 제주 P호텔 사진의 브랜드 로고 노출, 푸터 사업자정보(아직 임시 문구)
- 연습 글 '1'은 사용자가 삭제함(2026-09-29)
- 법령·기준 수치는 공공자료로 확인한 것만 쓰고 글 하단 <small>참고: …</small>에 출처 표기

## 다음에 할 만한 일
- 푸터 상호·사업자정보 입력
- 정보 글은 사용자와 번갈아 작성(사용자: 현장·후기형 / Claude: 비교·체크리스트형 제안). 새 글은 기존 글 목록 확인 후 주제 겹치지 않게, 초안 확인 후 게시
- 새 글 형식: 한 줄 결론(summary) + 비교표 + 질문형 소제목 + FAQ 3개 + 관련 글 2개 링크
- 네이버 서치어드바이저·구글 서치콘솔 등록(사이트맵 제출)
- 전용 도메인 연결(유료) 시 baseurl/CNAME 변경

## SEO·AI 노출 보완 이력 (2026-09-29)
- 메인: og:image 절대경로, canonical·og:url·og:site_name, Organization·WebSite·FAQPage JSON-LD, 비교·배출방식 이미지 alt 상세화
- 글 틀: 핵심 요약 박스, 글별 FAQ + FAQPage JSON-LD, Article JSON-LD에 image·logo 추가, 표 스타일(`assets/post.css` 끝)
- CMS: '핵심 요약', '자주 묻는 질문' 입력 칸 추가
- 정보 글 6개 전면 보강. 사용한 공공자료: 식품자동판매기영업 신고 제외 기준(소비기한 1개월 이상 완제품, 과천시 신고 안내), 냉장 0~10℃·냉동 -18℃ 이하·신선편의식품 5℃ 이하(식약처 안내, 식품저널 2022.12.21), 학교 고카페인 음료 판매 금지 2018.9.14(서울시 보건환경연구원)
- 남은 과제: 푸터 사업자정보(임시 문구 노출 중), 설치 후기 진위 확인, 글 대표 이미지(thumbnail) 없음, 메인 정보 섹션은 JS 로딩, 서치어드바이저·서치콘솔 인증 태그 없음

## 작업 방법 메모
- 화면 확인: 저장소 폴더에서 `python3 -m http.server 8765` 후 Playwright(PLAYWRIGHT_BROWSERS_PATH=/opt/pw-browsers)로 스크린샷. 모바일은 390×844 뷰포트 한 화면으로 찍을 것(구역 전체 캡처는 고정 헤더·하단 바가 중간에 찍혀 오해 생김). `html{scroll-behavior:auto}` 넣고 스크롤
- 작업 공간에서는 구글 폰트가 막혀 스크린샷 글씨체가 실제와 다를 수 있음
- 푸시 후 빌드 확인은 위 curl 명령으로 head_sha 일치 + success 확인
