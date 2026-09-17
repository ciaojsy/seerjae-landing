## 2026.09.17 작업

### 1. "Engineering Services" 섹션 추가
- "The Seerjae Philosophy" 섹션 다음에 신규 섹션(`.services`, id="services") 추가.
- 구성: eyebrow → 제목 → 소개 문장 → 01/02/03 카드(장비 소프트웨어 개발 / PLC·PC·Server 연동 / 장비 데이터 활용) → 하단 강조 문장.
- 기존 `.problem`/`.usecases` 섹션과 동일한 디자인 패턴(넘버링 카드 그리드) 사용, 850px/560px 반응형 규칙 추가.
- 한/영 토글(EN) 번역 문구 추가.

### 2. "Talk about your equipment" 섹션 콘텐츠 변경
- 제목: "장비 데이터부터 소프트웨어 개발까지 이야기해 주세요"로 변경.
- 본문: CYPRON 적용, 장비 소프트웨어 개발, 시스템 연동 등 과제 문의를 유도하는 문구로 변경.
- 영문 번역도 함께 수정.

### 3. 문의 유형(select#interest) 옵션 변경
- 변경 전: CYPRON 적용 가능성 상담 / 무료 데모 신청 / PoC·도입 컨설팅 / 기술 문의 / 기타
- 변경 후: CYPRON 적용 상담 / CYPRON 무료 데모 / 장비 SW 개발 / PLC·Server 연동 / 데이터 분석 / 기타
- 영문 옵션 목록도 동일하게 동기화.

### 4. 버그 수정 — Deployment 섹션 영문 번역 미반영
- `.deployment-note` 클래스가 `.process-note`와 중복되어 있어, 영문(EN) 전환 시 `setText('.deployment-note', ...)`가 첫 번째로 매칭된 process 섹션 문구만 바꾸고 실제 deployment 섹션 문장("동일한 CYPRON Core를 사용하며...")은 한글로 남아있던 문제 수정.
- 선택자를 `.deployment .deployment-note`로 한정하여 정상적으로 영문 전환되도록 수정.

### 5. 섹션별 배경 색상 위치 및 값

각 섹션의 배경색은 index.html의 `<style>` 블록 내 해당 클래스 선언부에서 지정됩니다.

| 섹션(제목) | 선택자 | 배경 값 |
|---|---|---|
| 공통 색상 변수 | `:root` | `--ink:#2c3d3a` / `--paper:#dfe6da` / `--line:#d5ded5` / `--muted:#60716a` / `--deeppink_accent`,`--blue`,`--sky`,`--mint`,`--deeppink_org_accent`: `#be7152` |
| Header(상단 메뉴) | `header` | `background:#162b26` |
| Hero | `.hero` | `radial-gradient(circle at 75% 35%, #718f7b 0, #466657 27%, #243d36 58%, #162b26 100%)` |
| Hero 신호 차트 바 | `.chart i` | `linear-gradient(180deg,#c9dacb,#6a9477)` |
| "Does this look familiar?" | `.problem` | `background:#edf0ed` |
| Problem 흐름의 CYPRON 단계 | `.problem-flow-step.cypron` | `background:#162b26` |
| "Why CYPRON" | `.proof` | `background:#f7f7f3` |
| "The Seerjae Philosophy" | `.philosophy` | `background:#edf0ed` |
| Process(감지~회복 5단계) | `.process` | `background:#ffffff` |
| Difference(비교) | `.difference` | `background:#f0f7f0` |
| 비교 카드 | `.compare-box`, `.compare-box.old`, `.compare-box.current` | `background:#f0f7f0` |
| "Deployment options" | `.deployment` | `background:#fff8fd` |
| "Start simply"(Why) | `.why` | `background:#ffffff` |
| "Engineering Services" | `.services` | `background:#ffffff` |
| "Where CYPRON fits" | `.usecases` | `background:#f7f7f3` |
| Founder's note(Insight) | `.insight` | `background:#f7f7f3` |
| Contact(문의 폼) | `.contact` | `linear-gradient(135deg,#243d36,#426152)` |
| Footer | `footer` | `background:#162b26` |

포인트 컬러(버튼·강조 텍스트·아이콘 등)는 대부분 `--deeppink_accent`(`#be7152`) 변수 하나로 통일되어 있으며, `:root`의 값만 바꾸면 사이트 전반의 포인트 컬러가 일괄 변경됩니다.

### 6. 배경 색상 변경 내역 (오늘 변경된 값)

| 섹션 | 선택자 | 위치(index.html) | 변경 전 | 변경 후 |
|---|---|---|---|---|
| "Deployment options" | `.deployment` | 118번째 줄 부근 | `background:#f5f1ea` | `background:#fff8fd` |
| "Where CYPRON fits" | `.usecases` | 132번째 줄 부근 | `background:#f0f7f0` | `background:#f7f7f3` |

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