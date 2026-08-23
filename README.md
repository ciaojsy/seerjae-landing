### 1. local에서 실행하기
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