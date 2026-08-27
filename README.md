## 2026.08.24 작업

### 수신 서비스 또는 서버 API에 연결 방법

#### 구성
- GitHub Pages + Google Apps Script + Google Workspace 조합
```
GitHub Pages의 신청 폼
        ↓ HTTPS POST
Google Apps Script 웹 앱
        ├─ Google Sheets에 신청 내용 저장
        ├─ Workspace 이메일로 관리자 알림
        └─ 신청자에게 접수 확인 메일 발송
```
#### 방법
- Google Sheet 생성
- Google Apps Script 에서 코드 추가
- 배포 정보
1) Id: AKfycbz5oLw8kohz3vqImBgs7szFfigUlPsZ5xLfXnO3QZrPWFbr_mj3ukebWQwkB1Etnoee
2) 웹앱 URL: https://script.google.com/a/macros/seerjae.com/s/AKfycbz5oLw8kohz3vqImBgs7szFfigUlPsZ5xLfXnO3QZrPWFbr_mj3ukebWQwkB1Etnoee/exec
3) 브라이저에서 URL입력시 아래 메시지로 테스트 완료
```
{
  "ok": true,
  "message": "CYPRON demo request endpoint is running."
}
```
4) Apps script를 수정하면 새배포를 할 것.
5) 구글 시트에 누적되고, soyoung.jun@seerjae.com으로 메일이 오고, 보낸 사람에게 자동 메일을 보내면 완료.

## 2026.08.23 작업

### 1. local에서 실행하기
#### 1) 웹 서버 실행
- 다음 명령을 입력 
> python -m http.server 8080
#### 2) 브라우저에서 아래 주소 오픈
- http://localhost:8080/index.html

### 2. 모바일 폰트 규칙
- Hero h1: 30px
- 섹션 h2: 26px
- Philosophy 제목: 26px
- 핵심 문장: 21px
- 비교 카드 제목: 21px
- 카드 소제목: 19px
- 설명 및 본문: 16px

### 3. 일반 웹(561px 이상) 폰트

현재 일반 웹(561px 이상)의 글자 크기는 다음과 같습니다.

| 구분 | 선택자 | 글자 크기 |
|---|---|---:|
| Hero 제목 | `.hero h1` | `24px–44px` 반응형 |
| 섹션 제목 | `h2` | `22px–38px` 반응형 |
| 핵심 문장 | `.proof-text` | `22px–38px` 반응형 |
| Philosophy 제목 | `.philosophy-quote` | `22px–38px` 반응형 |
| 비교 카드 제목 | `.compare-box strong` | `28px` |
| 단계 제목 | `.step h3` | `21px` |
| Why 카드 제목 | `.why-item b` | `20px` |
| 설명 문장 | `.section-intro` | `17px` |
| Hero 설명 | `.lead` | `18px` |
| 일반 본문 | `.philosophy-copy`, `.step p` | `16px` |
| Founder’s note 제목 | `.insight-title` | `18px` |
| Eyebrow | `.eyebrow` | `14px` |
| 상단 메뉴 | `.navlinks` | `15px` |

일반 웹은 화면 폭에 따라 제목 크기가 커지도록 `clamp()`를 사용하며, 모바일은 고정 크기로 위계를 맞춘 상태입니다. 관련 설정은 index.html에 있습니다.