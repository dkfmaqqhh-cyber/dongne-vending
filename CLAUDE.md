# 동네자판기 홈페이지 — 작업 인수인계 (새 채팅용)

새 채팅에서 이 저장소(`dkfmaqqhh-cyber/dongne-vending`)를 연결하면 이 문서부터 읽고 이어서 작업한다.

## 한눈에 보기
- **전용 도메인(120차, 2026-10-28): https://dongnevending.com** — 가비아에서 구입(3년, 만기 2029-10-28, 네임서버 가비아 기본). DNS 관리툴에 A @ 185.199.108~111.153 4개 + CNAME www → dkfmaqqhh-cyber.github.io. 사이트는 GitHub Pages(main)로 운영, `CNAME` 파일, `_config.yml` url/main_url=https://dongnevending.com, baseurl "". 넷리파이(myvending24)는 netlify.toml 301로 새 도메인에 넘기기만(전환 후 넷리파이 배포 1회만 필요). 이후 배포 크레딧 걱정 없음 → main 푸시 = 사이트 반영
- 2026-10-28 전환 반영: main 192888a(CNAME 포함) → GitHub Pages 빌드 성공, dongnevending.com 접속·canonical 확인. netlify 브랜치=192888a로 301 이동 설정 배포(마지막 넷리파이 배포, 이후 넷리파이 배포 불필요). 원격 domain-switch 브랜치는 권한 문제로 삭제 못 함(무시)
- 예전 넷리파이 주소 → 새 도메인 이동 사용자 확인 완료(10/28)
- 네이버 서치어드바이저 새 사이트 https://dongnevending.com 등록·소유확인 완료(10/28, 태그 1744e516…, 예전 b84886c7… 태그는 제거), 사이트맵·RSS 제출, 웹 페이지 수집(/, /posts/, /area/) 완료. 예전 넷리파이 사이트 등록과 넷리파이 프로젝트는 301 유지 위해 그대로 둠(2~3개월 뒤 정리)
- 구글 서치콘솔 새 속성 https://dongnevending.com/ (URL 접두어) 소유권 자동 확인(10/28, HTML 파일 googlef5d28c5141ab1faa.html — 루트 파일 삭제 금지)
- 구글 새 속성 sitemap.xml 제출 성공(10/28, 발견 18페이지). 주소 변경 도구는 예전 홈 301 확인 실패("페이지를 가져올 수 없음") — 예전 주소는 구글 색인이 거의 없어 건너뛰기로 함(나중에 다시 시도 선택)
- 구글 새 속성 색인 요청: / 완료(10/28), 할당량 초과로 남은 4개(/area/, /posts/hotel-vending/, /posts/hospital-vending/, /posts/baseball-vending/) 다음 날 진행
- GitHub Pages 설정 확인(10/28): 사용자 지정 도메인 dongnevending.com, DNS 확인 성공, HTTPS 강제 적용 체크됨
- 파워링크: 예전 동네자판기 비즈채널(넷리파이 주소)이 '사이트 운영자가 광고주 실명과 같은지 확인 불가'로 제재 → 사용자가 삭제 요청으로 삭제(10/28). 새 도메인으로 비즈채널 새로 등록 예정
- 파워링크 새 비즈채널 등록(10/28): 비즈채널 이름 "밴딩머신", 사이트 이름 "동네자판기", URL https://dongnevending.com — PC·모바일 검토중. 반려 시 사유 받아 대응(소유확인 태그·파일은 Claude가 추가)
- 전환 후 남은 일: 정보 글 자동 발행은 121차 섹션 참고
- (예전 대표 주소, 지금은 새 도메인으로 301 이동) https://myvending24.netlify.app/  (Netlify 프로젝트명 myvending24, 계정 dkfmaqhqo's team)
- 정보 글 목록: https://dongnevending.com/posts/ (github.io 주소는 새 도메인으로 자동 이동)
- 글 관리자(Sveltia CMS): https://dongnevending.com/admin/  (GitHub fine-grained 토큰, dongne-vending 저장소 Contents: Read and write)
- 배포: GitHub Pages (main 브랜치 / root, Jekyll 자동 빌드). 푸시 후 1~3분 뒤 반영
- 빌드 확인: `curl -s "https://api.github.com/repos/dkfmaqqhh-cyber/dongne-vending/actions/runs?per_page=1"`
- Netlify 동시 배포(준비 완료, 2026-09-30): `netlify.toml`(빌드 `bundle exec jekyll build --config _config.yml,_config_netlify.yml`, publish `_site`), `Gemfile`(github-pages 젬), `_config_netlify.yml`(baseurl "", url은 Netlify 주소 정해지면 입력). Netlify는 사용자 새 계정(GitHub dkfmaqhqo-crypto, 무료 월 300크레딧·배포 1회 15크레딧 ≈ 월 20회)으로 연결 진행 중 — dkfmaqhqo-crypto를 저장소 협업자로 초대·수락 완료, 다음은 dkfmaqqhh-cyber 계정으로 Netlify GitHub 앱 설치 후 Import. netlify.toml `ignore`로 CLAUDE.md·README만 바뀐 커밋은 배포 건너뜀. 커밋은 가급적 묶어서 올려 배포 횟수 절약 — 첫 빌드 로그 확인 필요(로컬에서 Jekyll 빌드는 rubygems 차단으로 검증 못 함)
- **Netlify 배포 제한(2026-09-30)**: Netlify는 `netlify` 브랜치만 배포(Production branch=netlify, Branch deploys=production only 설정 완료 확인 2026-09-30). 평소 작업·CMS 글은 main → GitHub Pages만 반영. 사용자가 "넷리파이에도 반영" 요청할 때만 `git push origin main:netlify`로 동기화(배포 1회 = 15크레딧). Netlify 계정: dkfmaqhqo's team(동네자판기 전용). 오늘의 철거(spacereborn-site)는 다른 Netlify 계정 — 섞어서 Import 금지
- 대표 주소: `_config.yml`의 `main_url` 하나로 canonical·og:url·og:image·JSON-LD·RSS·robots 전부 관리. 현재 **https://dongnevending.com** (2026-10-28 전환, 이전 myvending24.netlify.app)
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
- `index.html`은 맨 위에 front matter(layout: null)가 있어 Jekyll이 처리함(97차). 메인 '정보' 섹션(#info) 카드 6개는 Liquid(`site.posts limit:6`)로 HTML에 직접 생성 — fetch 스크립트 제거. `posts.json`은 남아 있지만 메인에서 안 씀
- `rss.xml` : RSS 2.0 피드(최근 30개, 네이버 서치어드바이저 RSS 제출용). base.html·index.html head에 rss 링크
- 로컬 미리보기는 Liquid 처리가 필요 → python-liquid로 index.html 렌더 후 확인(작업 방법 메모 참고)
- `admin/index.html`, `admin/config.yml` : Sveltia CMS (날짜는 date-only로 저장하도록 설정)
- `_config.yml` : baseurl ""(120차 도메인 전환 후), timezone Asia/Seoul, `future: true`, jekyll-sitemap. 전용 도메인 연결 시 baseurl "" + CNAME 추가
- `robots.txt` : /admin/ 제외, sitemap 링크

## 메인 페이지 섹션 순서 (id)
헤더 메뉴: 자판기종류(#types) · 설치장소·사례(#place) · 정보(#info)  — 모바일에서도 표시, '무료 상담' 헤더 버튼은 삭제함
1. 메인(hero2): 왼쪽 사진(`images/img_03_hero_notext.jpg` — '10,581개의 업체가…' 문구를 지운 버전, 원본 img_03_c3e3b4d691.jpg는 보관만) + 오른쪽 브라운 패널(106차: 영어 소제목 SMART VENDING SOLUTION·임대/설치/렌탈 칩 삭제, 소개 문구 1줄 '상품 구성부터 설치까지, 쉽고 빠르게 안내해드립니다.', 아이콘 타일 4개(116차에 숫자 3개로 교체), 무료 상담 신청→#contact·설치사례 보기 버튼 가운데 정렬 — 99차)
2. 가능 상품 목록(#types)
3. 운영의 차이(ops, 진한 브라운, 주간 매출 '예시' 그래프)
4. 자판기 종류 카드(#machines, 제목 '공간에 맞게 자판기 커스텀하세요.'): 스마트/확장형/냉장·냉동 쇼케이스/굿즈&담배. 스마트·쇼케이스는 '핵심 기능' 4개, 쇼케이스는 사진 2장 자동 슬라이드. 모바일은 선택 시 카드로 자동 스크롤
5. 불편했던 기존 방식 vs 스마트 솔루션 이미지
6. 배출 방식 이미지
7. 설치 장소(#place) — 모바일 2열
8. 설치사례(#case) 20곳(111차, 2026-10-14: 인천 A 무인카페 img_35·양주 A 키즈카페 img_36·제주 H 상점 img_37·대구 B 학원 img_38 추가, PC 4열이 꽉 차도록 20곳. 보류: 경기(이름 모름)·제주 L호텔(타사 자판기 함께 찍힘). 제주 P호텔 로고 사진은 사용자가 그대로 두기로 함) — 4개 표시 + '더보기(+16)'로 펼침 / 설치 후기 4개 가로 자동 슬라이드
9. 자판기 설치·운영 정보(#info) — posts.json 카드 6개 + 전체 보기
10. 무료 상담(#contact, 상담 가이드형): 실시간 채팅(흰 배경+오렌지 테두리, 95차) / 빠른 전화 연결(흰 배경+브라운 테두리) / 무료 견적 신청(오렌지) 3버튼. 버튼 아래 전화번호 안내 문구(cg-note)는 삭제함
11. (설치 진행 과정 섹션은 105차에 삭제 — 무료 견적 순서와 겹침. #contact의 견적 순서를 5단계로 보완: 기본 정보 전달 → 설치 환경 확인 → 상담·제품 제안 → 방문·설치 진행 → 운영 시작, 제목 '무료 견적부터 설치까지') / FAQ / FAQ 아래 특징 4칸 → 맨 아래 전화 상담 바 순서(101차). 전화 상담 바(설치·견적 전화 상담 010-7990-2378, 전화 걸기→tel / 문의 남기기→네이버폼), 특징 4칸(102차: 모든 칸 같은 크기, 모바일은 두 줄 가운데 정렬. 24인치 터치 키오스크·4개 국어 화면·설치일부터 3년 무상 A/S·1080×1920 매장 광고 송출 — 사용자가 사실 확인, 100차, .bc-section) / 모바일 하단 고정바(전화·카톡·상담신청). 110차(2026-10-13): 맨 아래 하단 정보 footer(.site-foot: 동네자판기 · 상담 전화 · 개인정보 처리방침 링크 · ©) 추가 — 사업자정보(상호·대표자·사업자등록번호·주소)는 아직 없음, 확정되면 .sf-biz에 추가. 글 페이지(base.html) 푸터에도 개인정보 처리방침 링크 추가

## PC 떠 있는 상담 버튼(112차, 2026-10-14)
- `_includes/float-cta.html`(CSS 포함): 오른쪽 아래 고정 세로 3개 — 카카오톡 상담(노랑)·무료 견적받기(오렌지, 네이버폼)·전화 상담(브라운, tel). 같은 폭(168px)
- 위치 bottom:84px(114차: 넷리파이 무료 플랜 "Powered by Netlify" 배지가 오른쪽 아래에 떠서 겹침 → 위로 올림. 배지는 Project configuration > General > Powered by Netlify badge에서 끌 수 있음)
- 메인은 첫 화면에서 숨기고 600px 이상 스크롤하면 나타남(115차, include 인자 after=600 — 첫 화면 버튼과 겹침 방지). 글 페이지는 항상 표시
- PC에서만 표시: 메인 `{% include float-cta.html min=901 after=600 %}`(모바일 하단바가 900px 이하), 글·처리방침 페이지 base.html `min=641`(bmob이 640px 이하)
- 로컬 렌더 스크립트(scratchpad render.py)는 Jekyll include를 정규식으로 처리하도록 수정함

## 콘텐츠 운영 방침(113차, 2026-10-21 사용자 결정)
- 정보 글은 꾸준히 웹사이트에 등록. 지역 랜딩페이지는 `/area/` 하나만 두고, 나머지는 정보 글 안에 장소·상품·지역 SEO 키워드를 자연스럽게 넣어 업데이트
- 키워드 방향(사용자 참고 자료: 구매 전환 높은 키워드): 장소(호텔·병원·골프장 자판기), 상품(디저트·생활용품·세차용품 자판기), 운영 목적(무인자판기·멀티자판기). 렌탈·무상만 찾는 검색은 파워링크 제외 키워드로 거르기(사이트에서 '렌탈·임대'는 유지 — 사용자 핵심 키워드)
- 지역 이름은 실제 사례 있는 곳만 '사례'로 쓰고, 없는 지역은 '설치 가능'으로만. 지역명 나열(도배) 금지
- 다음 글 후보: 병원 자판기, 골프장 자판기(사례 없음 → 정보성), 디저트·세차용품은 취급 가능 여부 사용자 확인 후
- `/area/` 지역별 설치 안내(area/index.html, base 레이아웃): 지역·사례 데이터는 118차부터 `_data/areas.yml`(id·name·sub·page·cases[name,type,img]) → 새 설치사례 생기면 여기와 메인 #case 둘 다 추가. 지역 앵커(#seoul #gyeonggi #incheon #gangwon #chungcheong #jeolla #gyeongsang #jeju) — 광고 연결용. FAQ 3개 + FAQPage JSON-LD 인라인. CSS는 assets/post.css 끝(.ar-*). 링크: 메인 설치사례 아래 '지역별 설치사례 보기', 메인·글 페이지 푸터
- 정보 글 8번째(2026-10-21): `/posts/hotel-vending/` '호텔 자판기 설치, 제주·대구 사례로 본 숙박업소 위치와 상품 구성' — 서울·경기·인천·강원·제주 언급, FAQ 4개. 사용자 확인(10/21): 제주 P호텔은 수영장 앞 설치, 수영모 판매 구성 가능 → 글에 반영. 충전 케이블·마스크는 일반 예시로만 둠(취급 여부 미확인)

## 첫 화면 숫자 3개(116차, 2026-10-21)
- 사용자 참고 화면(건강음료 자판기 랜딩: 큰 숫자 3개·실제 설치 사진+장소 표시)에서 착안. 아이콘 상자 4개(카드·간편결제/24시간/원격 재고/맞춤 구성, .h2-tiles)를 숫자 3개(.h2-stats)로 교체: 24인치 터치 화면 / 4개 국어 화면 지원 / 3년 무상 A/S — 사용자가 사실 확인
- 다음(보류): 첫 화면 사진을 실제 설치사례(예: 제주 P호텔 수영장 앞)+장소 표시로 교체 — 사용자가 원본 고화질 사진 찾는 중(현재 사례 사진은 가로 300~420px라 부족)
- 320px 하단 고정바 글자 줄바꿈(78px) 수정 → 한 줄(51px)

## 정보 글 자동 발행(121차, 2026-10-28 사용자 결정: 주 3회 수·목·금 오전 7시 무렵, 확인 없이 바로 게시)
- 예약 작업: "동네자판기 정보글 자동 발행 (수·목·금)" trig_01UCi3CwxJvu2d18418vBeBm, 매주 수·목·금 06:55(KST), 클라우드 실행·자동 승인·완료 시 휴대폰 알림. 첫 실행 2026-10-29(목)
- 예약 작업이 이 섹션을 읽고 '주제 대기열'에서 아직 안 쓴 첫 주제로 글 1편을 써서 main에 올림(GitHub Pages → https://dongnevending.com 자동 반영, 비용 없음)
- 주제 대기열(위에서부터, 다 쓰면 [완료 날짜 slug] 표시). '문의 증가'는 사용자가 말한 사실(10/28: 주차장·운동센터·호텔 굿즈·냉장 고기 자판기 문의가 늘고 있음) — 글에는 "최근 상담 문의가 늘고 있는 분야"로만 쓰고 설치사례처럼 쓰지 말 것
  1. 주차장 자판기(문의 증가) — 무인 주차장·주차타워·공영주차장 이용객 음료·간식·차량용품, 전원·야외 설치 확인
  2. 운동센터·피트니스 자판기(문의 증가) — 운동 전후 음료·단백질 음료, 대구 무인 탁구매장 사례 연결, 기존 items-by-space와 겹치지 않게 깊게
  3. 호텔 굿즈 자판기(문의 증가) — 호텔 로고 굿즈·어메니티·기념품, 굿즈 밴딩머신, 제주 P호텔 수영장 앞(수영모) 사례, hotel-vending 글과 겹치지 않게 '굿즈' 중심
  4. 냉장 고기(정육) 자판기(문의 증가) — 냉장·냉동 쇼케이스, 보관 온도, 식육 판매 관련 영업 신고 등은 공공자료로 확인된 것만(확인 못 하면 "관할 시·군·구청 확인 필요"로만)
  5. 골프장 자판기 — 사례 없음, 정보성
  6. 무인매장·무인카페 멀티자판기 — 안동·인천·청주 무인카페 사례
  7. 아파트·오피스텔 공용공간 자판기 — 관리 주체 허락, 입주민 이용
  8. 공장·교대근무 사업장 자판기 — 구미 1·2동, 김천 사무실, 정읍 구내식당 사례
  9. 키즈카페·놀이시설 자판기 — 양주 키즈카페 사례
  10. 학원·스터디카페 자판기 — 대구 B 학원 사례
  (대기열이 비면 기존 글과 겹치지 않는 새 주제 3개를 이 목록에 추가하고 그중 첫 번째로 작성)
- 123차 보완(GEO 교육자료 반영, 2026-10-28): 모든 글에 '이런 곳에 맞습니다 / 이런 곳엔 다른 방법이 나을 수 있습니다' 소제목 1개 필수(예: 이용 인원이 매우 적은 곳, 전원·반입이 어려운 곳 → 정수기·간식 바구니·소형 쇼케이스 등 대안 언급). 과장 형용사(최고·엄선·체계적·책임) 금지. FAQ 구조화 데이터는 유지하되 'AI 인용 효과'를 근거로 쓰지 말 것(구글 FAQ 리치결과 2026-05 종료)
- 작성 규칙: 기존 글 형식(front matter: title·date(날짜만)·tag·cover·color·thumbnail ""·description(150자 이내, '무인자판기' 1회)·summary·faq 3~4개) + 비교표 1~2개 + 질문형 소제목 + 관련 글 2개 링크({{ '/posts/slug/' | relative_url }}) + 마지막 💡 상담 안내 1줄. 제목 45자 안팎, 키워드(장소+자판기 설치) 앞쪽
- 사실 규칙: 동네자판기는 LK 자판기 공식 판매·설치점(사용자 확인) / 작성자는 '동네자판기'(박시연 쓰지 말 것) / 동네자판기 확인 사양만(24인치 터치·4개 국어·설치일부터 3년 무상 A/S·1080×1920 광고 송출·전국 설치·1대 설치비 포함 23만 원부터·2대 이상 할인) / 설치사례는 _data/areas.yml에 있는 것만, 사진에 근거한 내용은 "(설치 사진 기준)" / 법령·기준 수치는 공공자료로 확인한 것만 + 글 하단 <small>참고: …</small> / 금액·실적·후기 지어내기 금지 / 광고·홍보성 표현 금지(정보성·후기성, SEO+AEO+GEO)
- 발행 절차: _posts/YYYY-MM-DD-slug.md 작성 → 깨진 링크·front matter 확인 → 커밋(작성자 Claude, 메시지 끝에 Co-Authored-By/Claude-Session 줄) → main 푸시 → 빌드 success 확인 → 이 섹션 대기열에 [완료] 표시 + 키워드 매핑에 추가 → 프로젝트 문서 동기화 → 사용자에게 글 제목·주소 + "네이버 웹 페이지 수집·구글 색인 요청에 이 주소를 넣어 주세요" 알림
- 사실 확인이 꼭 필요한데 확인이 안 되면 게시하지 말고 다음 주제로 넘어가거나, 초안만 만들고 사용자에게 무엇을 확인해야 하는지 알림

## 정보 글 9번째(119차, 2026-10-23)
- `/posts/hospital-vending/` '병원 자판기 설치, 대구·하남 사례로 본 대기실 위치와 상품 구성' — 대구 A 병원(사진상 음료+티슈 등 생활용품), 하남 S 치과의원(대기 공간 벽면, 사진 기준). 사용자 미확인 상태로 '설치 사진 기준' 표기. 지역 페이지 경상·경기 '함께 볼 글'에 연결

## 정보 글 10번째(119차, 2026-10-23)
- `/posts/baseball-vending/` '야구장 자판기 설치, 음료부터 굿즈·포토카드·밀키트까지 상품 구성' — 사용자 의견(업종 다양화, 굿즈·포토카드, 밀키트 증가)을 '현장에서 느끼는 흐름'으로 표기. 야구장 사례 없음 → 정보성. 프로야구 구장 도시(서울 잠실·고척, 인천, 수원, 대전, 광주, 대구, 부산, 창원) 표 + 같은 지역 우리 사례·지역 페이지 연결('야구장이 아니라 같은 지역 다른 업종 사례' 명시). 구단·구장 정식 명칭은 넣지 않음. FAQ 4개

## 지역별 상세 페이지(118차, 2026-10-23 사용자 승인: 절충안)
- 사례 있는 4개 지역만 상세 페이지: /area/gyeongsang/(대구·경북·경남, 10곳) /area/gyeonggi/(경기 4곳+인천 언급) /area/jeju/(2곳) /area/jeolla/(전라·광주 2곳). 파일 area/<id>.md, 레이아웃 `_layouts/area.html`(사례 사진·본문·함께 볼 글·지역 FAQ+FAQPage·BreadcrumbList JSON-LD·상담 버튼·다른 지역 링크)
- 사례 데이터는 `_data/areas.yml` 하나로 관리(허브 /area/와 상세 페이지 공용). 새 사례 → areas.yml + 메인 #case에 추가. 상세 페이지 있는 지역은 `page:` 값 → 허브에 '자세히 →' 링크
- 원칙: 지역명만 바꾼 복제 페이지 금지(구글 도어웨이 정책). 지역마다 실제 사례·업종별 내용·지역 FAQ가 달라야 함. 2~3개월 서치콘솔 확인 후 사례 생긴 지역부터 확장
- 키워드 → 주소 매핑: 무인자판기 설치/임대·렌탈 → / | 지역별 자판기 설치 → /area/ | 대구·구미·경북 자판기 설치 → /area/gyeongsang/ | 경기(화성·하남·부천) 자판기 설치 → /area/gyeonggi/ | 제주 자판기 설치 → /area/jeju/ | 광주·전라 자판기 설치 → /area/jeolla/ | 호텔 자판기 → /posts/hotel-vending/ | 자판기 설치 비용 → /posts/cost-factors/ | 자판기 렌탈·임대·구매 → /posts/rent-vs-lease/ | 스마트·키오스크 자판기 → /posts/smart-vs-basic/ | 냉장·냉동 자판기 → /posts/freezer-showcase/ | 자판기 설치 절차 → /posts/install-process/ | 회사·학교·병원 자판기 상품 → /posts/items-by-space/ | 설치 전 확인 → /posts/check-before-install/ | 병원 자판기 → /posts/hospital-vending/ | 야구장 자판기·굿즈 자판기·밀키트 자판기 → /posts/baseball-vending/ | (예정) 골프장 자판기

## GEO 교육자료 점검(123차, 2026-10-28)
- 자료: 바인그룹 'GEO 1회차' (Google 공식: AI 전용 마크업 불필요, FAQ 리치결과 종료, llms.txt 무관 / 검색봇은 열고 학습봇은 정책대로 / 지역명 바꾼 페이지 대량 생산 금지 / 측정: 서치콘솔+애널리틱스+프롬프트 감사)
- 반영: 큰 사진 7장 압축(1,907KB→989KB, 가로 최대 1200px·품질 80, 파일명 그대로), 자동 발행 규칙에 '맞는 경우/안 맞는 경우' 추가
- 진행 중: 네이버 애널리틱스(사용자 선택) — 사용자가 analytics.naver.com에 dongnevending.com 등록 후 스크립트 ID 전달 예정 → index.html·base.html에 삽입 + 개인정보 처리방침 '분석 도구 안 씀' 문구 수정
- 다음 후보: A/S·계약 안내 페이지(고장 연락 방법·A/S 범위·계약 기간·철거 조건 — 사용자 정보 필요), 상담에서 자주 받는 질문 10개(사용자 제공) → FAQ·글 주제, 월 1회 프롬프트 감사(ChatGPT 등에 고정 질문 10개)
- robots.txt는 전체 허용(/admin/만 차단) 유지 — 학습봇 차단 여부는 사용자 결정 사항(현재 허용)

## 작성자 표시(117차, 2026-10-23 → 122차 2026-10-28 변경)
- 122차: 박시연은 사용자 실명이 아님 → 작성자를 '동네자판기'로 변경(표지 '동네자판기 · 날짜', `_config.yml` author_name, Article JSON-LD author=Organization). 박시연 이름은 사이트 어디에도 쓰지 말 것
- 운영자 정보(122차): 사용자 = 개인 명의 광고 계정, 사이트 표시 이름은 '동네자판기', 'LK 자판기 공식 판매·설치점'(사용자 확인 2026-10-28). 하단: '운영: 동네자판기 (LK 자판기 공식 판매·설치점) · 전화 010-7990-2378'(메인 .site-foot, 글 base.html .bf). 이메일은 넣지 않음(사용자 결정). 실명은 사이트에 공개하지 않음 — 파워링크 실명 확인은 필요하면 고객센터·서류로
- 글 수정 시 front matter `last_modified_at: YYYY-MM-DD` 넣으면 표지에 '· 수정 날짜' 표시 + JSON-LD dateModified 반영
- FORTIFY SEO 교육 PPT(2026.7.10) 점검(10/23): 남은 보완 = 넷리파이 배지 끄기, 구글 서치콘솔 사이트맵 제출 확인·새 주소 색인 요청, 키워드→URL→제목 매핑표, 네이버폼 질문 수 확인. 지역 페이지는 절충안(사례 있는 4개 지역만 상세 페이지)으로 결정 — 118차, 매핑표도 118차 항목에 정리

## 버튼·문구(107차, 2026-10-03)
- 첫 화면 오렌지 버튼: '우리 공간 견적 받아보기'(→#contact), 상태 문구: '전국 설치 가능 · 무료 견적', 모바일 하단 고정바 오른쪽: '무료 견적받기'(→네이버폼). 사용자가 '무료 견적받기' 표현을 선호

## 첫 화면 전광판 문구(108차, 2026-10-03)
- 상태 문구가 오른쪽→왼쪽으로 흐름(.h2-ticker, CSS 애니메이션 16초 반복, 마우스 올리면 멈춤, '동작 줄이기' 설정 사용자는 멈춤). 내용: '전국 설치 가능 · 무료 견적 · 2대 이상 설치 시 할인 가능' — 가격 줄 옆 '2대 이상 설치 시 할인' 문구는 여기로 옮기며 삭제
- 가격 상자(.h2-price-main) 크기 축소(109차: 글자 14px·금액 16px, 모바일 13.5px·15px). 115차(2026-10-21): 탁한 배경에서 잘 안 보인다는 의견 → 밝은 크림 바탕(#fff4e6)+진한 브라운 글씨+오렌지 금액으로 변경
- 주의: .h2-top 그리드 자식에 min-width:0 필요(없으면 전광판 글자 폭 때문에 모바일 가로 스크롤 생김)

## 전국 설치·가격 안내(103차, 2026-10-03 사용자 제공 정보)
- 전국 설치 가능 / 1대 기준 설치비 포함 23만 원부터 / 2대 이상 할인
- 반영 위치: 첫 화면 상태 문구("전국 설치 가능 · 무료 상담 진행 중") + 가격 줄(.h2-price, 첫 화면에는 "1대 기준" 문구 빼고 "2대 이상 설치 시 할인"만 — 104차), 맨 아래 특징 6칸(PC 3열·모바일 2열), FAQ '설치 비용은 얼마인가요?' 답변 + 새 FAQ '지방이나 먼 지역도 설치가 되나요?'(화면·JSON-LD 둘 다), meta/og description, Organization JSON-LD areaServed·description

## 디자인 기준
- 톤: 크림·샌드 배경 그라데이션 + 진한 브라운(#3b2a20) + 오렌지(#ff5b14) 강조
- 글씨체: 나눔고딕(Nanum Gothic), 작은 글씨는 굵기 400~700
- 로고: images/img_02_... (주황 자판기 + '동네자판기'), 파비콘 img_01_...
- PC/모바일(390·360·320px) 모두 가로 스크롤 없게 확인하며 작업

## 사용자 선호·주의
- 답변은 한국어, 근거 없는 내용은 "잘 모르겠습니다/추측입니다"로 구분, 사실은 답변 끝에 정리
- 광고·홍보성 문구 배제, 정보성·후기성 글(SEO+AEO+GEO 통합형)
- 지어낸 후기·수치를 실제처럼 쓰지 않는다. 설치 후기 4개(김**, 박**, 이**, 최**)는 사용자가 '그대로 사용 가능'으로 확인함(2026-09-29)
- 사진 속 LK 브랜드 표시는 사용해도 된다고 사용자가 확인함
- 정보 글 대표 사진(thumbnail)은 당분간 넣지 않고 색상 표지(color)로 운영하기로 함
- 확인 필요 항목: '방문 접수' 표현, 제주 P호텔 사진의 브랜드 로고 노출
- 연습 글 '1'은 사용자가 삭제함(2026-09-29)
- 법령·기준 수치는 공공자료로 확인한 것만 쓰고 글 하단 <small>참고: …</small>에 출처 표기

## 네이버 파워링크 검수 대응(110차, 2026-10-13)
- 검수 지연 원인 추정(다른 AI 분석 참고): 사업자정보 미표시·'담배' 문구·개인정보 처리방침 없음·netlify.app 주소(영향 잘 모르겠음)
- 조치: '굿즈 & 담배 밴딩머신' → '굿즈 밴딩머신', 설명 '굿즈·캐릭터 상품 등 특화 상품…'(사용자 결정). 사이트에 '담배' 표현 없음
- 개인정보 처리방침 페이지 `privacy/index.html`(/privacy/, base 레이아웃, 표 스타일 .pv는 assets/post.css 끝). 홈페이지 자체 수집 없음, 네이버폼·카톡·전화 문의 기준, 시행일 2026-10-13
- 남은 일: 사업자정보 받으면 footer에 추가, 비즈채널 반려 사유 확인, 넷리파이 배포 완료(2026-10-13 netlify=4bb7739, 2026-10-14 netlify=4b99ab1 — 설치사례 20곳·PC 상담 버튼 반영, 2026-10-23 netlify=a12b647 — 지역 페이지·호텔 글·첫 화면 숫자·작성자 반영, 같은 날 netlify=067f760 — 병원·야구장 글 반영. 사용자가 넷리파이 배지 끔(10/23)). 파워링크 노출제한 원인은 비즈채널 주소 오타(myvending24.netlife.app) — 올바른 주소 https://myvending24.netlify.app 비즈채널로 새로 연결 진행

## 다음에 할 만한 일
- (선택) 사업자정보가 확정되면 메인에 footer 다시 추가
- 정보 글은 사용자와 번갈아 작성(사용자: 현장·후기형 / Claude: 비교·체크리스트형 제안). 새 글은 기존 글 목록 확인 후 주제 겹치지 않게, 초안 확인 후 게시
- 새 글 형식: 한 줄 결론(summary) + 비교표 + 질문형 소제목 + FAQ 3개 + 관련 글 2개 링크
- 네이버 서치어드바이저·구글 서치콘솔 등록(사이트맵 제출)
- 전용 도메인 연결(유료) 시 baseurl/CNAME 변경

## SEO·AI 노출 보완 이력 (2026-09-29)
- 메인: og:image 절대경로, canonical·og:url·og:site_name, Organization·WebSite·FAQPage JSON-LD, 비교·배출방식 이미지 alt 상세화
- 글 틀: 핵심 요약 박스, 글별 FAQ + FAQPage JSON-LD, Article JSON-LD에 image·logo 추가, 표 스타일(`assets/post.css` 끝)
- CMS: '핵심 요약', '자주 묻는 질문' 입력 칸 추가
- 정보 글 6개 전면 보강. 사용한 공공자료: 식품자동판매기영업 신고 제외 기준(소비기한 1개월 이상 완제품, 과천시 신고 안내), 냉장 0~10℃·냉동 -18℃ 이하·신선편의식품 5℃ 이하(식약처 안내, 식품저널 2022.12.21), 학교 고카페인 음료 판매 금지 2018.9.14(서울시 보건환경연구원)
- 네이버 서치어드바이저 인증 태그(naver-site-verification b84886c7…) index.html·base.html head에 추가(2026-09-30, 대표 주소 myvending24.netlify.app 기준)
- 네이버 서치어드바이저: 소유확인 완료, robots.txt 수집 확인, 웹 페이지 수집 요청 8개(메인·/posts/·글 6개)·사이트맵·RSS 제출 완료(2026-09-30). 색인 상태 확인은 수집 전이라 결과 없음 → 며칠 뒤 재확인. 새 글 올리면 '요청 → 웹 페이지 수집'에 글 주소 넣기 권장
- 구글 서치콘솔: URL 접두어 방식(https://myvending24.netlify.app/), HTML 파일 인증 `googlef5d28c5141ab1faa.html`(루트, 삭제 금지) 추가(2026-09-30). 사용자가 HTML 태그 방식으로 확인해서 google-site-verification 메타태그(PThl-v7p…)도 index.html·base.html head에 추가. 다음: 확인 → Sitemaps에 sitemap.xml 제출
- 관리자 페이지(admin/index.html)에 front matter(sitemap: false) 추가해 사이트맵에서 제외
- 2026-10-23: 네이버 웹 페이지 수집 요청 6개 완료(/area/, /area/gyeongsang/, /area/gyeonggi/, /area/jeju/, /area/jeolla/, /posts/hotel-vending/). 구글 색인 요청은 할당량 초과로 못 함 → 다음 날 다시 시도(사이트맵 제출돼 있으면 자동 수집도 됨). 같은 날 네이버 수집 요청 2개 추가 완료(/posts/hospital-vending/, /posts/baseball-vending/). 구글 남은 요청 8개: /area/, hotel·hospital·baseball 글, 지역 4개

## 작업 방법 메모
- index.html에 Liquid가 있으므로 로컬 화면 확인 시 `pip install --break-system-packages python-liquid` 후 site.posts를 _posts front matter로 만들어 렌더(relative_url 필터: 도메인 전환 후 baseurl ""이므로 앞에 아무것도 안 붙임 — scratchpad render.py는 아직 '/dongne-vending' 기준, 미리보기만 영향)
- 화면 확인: 저장소 폴더에서 `python3 -m http.server 8765` 후 Playwright(PLAYWRIGHT_BROWSERS_PATH=/opt/pw-browsers)로 스크린샷. 모바일은 390×844 뷰포트 한 화면으로 찍을 것(구역 전체 캡처는 고정 헤더·하단 바가 중간에 찍혀 오해 생김). `html{scroll-behavior:auto}` 넣고 스크롤
- 작업 공간에서는 구글 폰트가 막혀 스크린샷 글씨체가 실제와 다를 수 있음
- 푸시 후 빌드 확인은 위 curl 명령으로 head_sha 일치 + success 확인

## 키워드 조화·기술 보완 이력 (2026-09-30, 97차)
- 대표 키워드 연결: 글 description에 '무인자판기' 1회씩, 스마트 글에 '스마트 밴딩머신' 병기, 설치 과정 글 제목 "자판기 설치 절차와 기간…", 렌탈 글 제목 "자판기 렌탈·임대·구매 차이…" + 소제목에 '자판기 렌탈·임대/구매', 공간별 글에 아파트·오피스텔 / 무인매장·PC방 소제목 추가, 쇼케이스 소제목 보강
- 메인 H2 문구: "무인자판기 설치하면 달라지는", "무인자판기 실제 설치 현장을", "무인자판기 설치는 이렇게 진행됩니다"(105차에 섹션째 삭제), "자판기 설치 전 많이 묻는 질문"
- 메인 이미지 31개 loading="lazy" decoding="async"(로고·첫 화면 사진 제외)
- 보조 키워드(사용자 제안, 98차): '키오스크 자판기'(스마트 밴딩머신 설명·메인 meta description·스마트 글 소제목), '멀티자판기'(확장형 밴딩머신 설명·meta description·공간별 글 무인매장 부분). 과하게 반복하지 말 것
- 정보 글 7번째(Claude 작성, 2026-10-03): `/posts/cost-factors/` '자판기 설치 비용은 왜 다를까? 견적이 달라지는 6가지 요소' — 금액 없이 상담 유도. 사용자 방침: 자세한 가격·실적 수치는 사이트에 넣지 않고 상담으로 연결(광고스러운 표현 지양)
- 다음 추천: 설치사례 지역별 후기형 글(사용자)
