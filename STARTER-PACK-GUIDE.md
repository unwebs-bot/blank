# WP Starter Pack - 새 프로젝트 초기 설정 가이드

새 프로젝트를 시작할 때 Claude에게 아래 항목들을 순서대로 지시하세요.

---

## 1. 기본 정보 교체

> "inc/config.php에서 회사 정보를 아래 내용으로 교체해줘"

- `company` 배열: 회사명, 대표자, 전화번호, 팩스, 이메일, 주소, 사업자번호
- `site` 배열: 사이트 타이틀, 설명, 키워드
- `sns` 배열: SNS 링크 (없으면 비워두기)

## 2. 네비게이션 메뉴 구성

> "inc/config.php의 nav 배열을 아래 메뉴 구조로 변경해줘"

프로젝트에 맞는 GNB 메뉴와 서브메뉴 구조를 알려주면 됨.

## 3. 테마 정보 수정

> "style.css의 테마 이름과 설명을 [프로젝트명]으로 변경해줘"

## 4. 디자인 컬러 변경

> "assets/css/layout/layout.css에서 --uw-primary 색상을 [#컬러코드]로 변경해줘"

필요하면 `--area-width`, `--uw-header-height` 등 레이아웃 변수도 같이 조정.

## 5. 이미지 교체

직접 교체할 파일:
- `assets/images/logo.png` - 사이트 로고
- `assets/images/og-image.jpg` - SNS 공유 시 썸네일

## 6. SMTP 메일 설정

> "wp-config.php에 SMTP 상수를 추가해줘"

```php
define('SMTP_HOST', 'smtp.gmail.com');
define('SMTP_PORT', 587);
define('SMTP_SECURE', 'tls');
define('SMTP_USERNAME', '메일주소');
define('SMTP_PASSWORD', '앱 비밀번호');
```

Gmail 사용 시 Google 계정에서 앱 비밀번호 발급 필요.

## 7. 워드프레스 관리자 설정

직접 설정할 항목:
- 설정 > 퍼머링크: `/%postname%/`
- 설정 > 읽기: 정적 첫 페이지 지정
- UW 게시판 > 게시판 생성 (필요 시)
- UW 문의폼 > 문의폼 생성 + 알림 이메일 설정
- UW 갤러리 > 갤러리 생성 (필요 시)

## 8. 페이지 생성

> "아래 페이지들을 만들어야 하는데 필요한 템플릿 파일 만들어줘"

기본 제공 템플릿:
- `front-page.php` - 메인 페이지
- `page-templates/page-company-intro.php` - 회사소개

추가 페이지는 프로젝트에 맞게 요청.

## 9. 개인정보처리방침 수정

> "inc/config.php의 개인정보처리방침을 [회사명]에 맞게 수정해줘"

이용약관도 같은 파일에 있음.

---

## 참고: 숏코드

| 기능 | 숏코드 예시 |
|------|------------|
| 게시판 | `[uw_board name="notice"]` |
| 게시판 스킨 | `[uw_board name="notice" skin="style02"]` |
| 최신글 | `[latest_posts id="notice" limit="3" url="/notice/"]` |
| 문의폼 | `[uw_inquiry id="contact"]` |
| 갤러리 | `[uw_gallery id="press" style="grid"]` |
| 영상갤러리 | `[uw_gallery id="video" style="video"]` |

## 참고: 게시판 스킨

| 스킨 | 형태 |
|------|------|
| style01 | 테이블형 (기본) |
| style02 | 미니멀 카드 |
| style03 | 썸네일 카드 |
