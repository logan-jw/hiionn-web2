# Hiionn 소개 웹페이지

해외 환자 유치 온·오프라인 통합 파트너 **Hiionn**((주)아크로모빌리티) 브랜드 소개 원페이지 사이트입니다.

## 구성

```
hiionn-web/
├── index.html      단일 파일 랜딩 페이지 (HTML + CSS + JS 인라인)
├── images/         로고 및 콘텐츠 이미지 (상대경로 ./images/ 참조)
│   └── demo/       미니프로그램 데모용 이미지 (AI 생성, 특정 병원 아님)
└── README.md
```

| 파일 | 용도 |
|---|---|
| `images/logo-horizontal.png` | 가로 로고 (헤더·푸터) |
| `images/logo-symbol.png` | 심볼 로고 (히어로·파비콘·OG 이미지) |
| `images/online-content.jpg` | 온라인 파트 섹션 |
| `images/offline-content.jpg` | 오프라인 파트 섹션 (실제 MOU 현장) |
| `images/content-vlog.jpg` | 콘텐츠 전략 — VLOG |
| `images/content-interview.jpg` | 콘텐츠 전략 — 인터뷰 |
| `images/content-review.jpg` | 콘텐츠 전략 — 후기 |
| `images/demo/clinic.jpg` | 데모 — 병원 리셉션 (일반 이미지) |
| `images/demo/treatment.jpg` | 데모 — 진료실 (일반 이미지) |
| `images/demo/academy.jpg` | 데모 — 세미나실 (일반 이미지) |
| `images/demo/hero-abstract.jpg` | 데모 — 배너 배경 |

각 사진에는 `-480` / `-800` 등 접미사가 붙은 **반응형 축소본**이 함께 있으며
`srcset`으로 화면 크기에 맞는 파일만 내려받습니다. 원본을 교체할 때는
축소본도 같이 갱신해야 합니다.

## 로컬에서 보기

`index.html`을 브라우저로 바로 열면 됩니다. 또는 로컬 서버 실행:

```bash
python -m http.server 8000
# http://localhost:8000
```

## 배포

GitHub Pages (`main` 브랜치 `/` 루트)로 배포됩니다.
`index.html`을 수정해 커밋·푸시하면 1~2분 내 자동 반영됩니다.

## 기술 사항

- 외부 의존성 없음 (Google Fonts만 CDN 로드)
- 모든 이미지는 상대경로 `./images/` 참조 — 외부망·오프라인 환경에서도 동작
- 반응형: 1180px / 980px / 768px / 560px 브레이크포인트
- 반응형 이미지: `srcset` + `sizes`로 모바일에서 축소본만 전송
- SEO: meta description, Open Graph 태그, 파비콘
- 접근성: `prefers-reduced-motion` 대응, 키보드로 FAQ 토글 가능
- 성능: 사진 `loading="lazy"`, `width`/`height` 명시로 레이아웃 시프트 방지

## 본문 강조 표기

본문에서 핵심 문구는 아래 두 클래스로 강조합니다.

| 클래스 | 의미 | 표현 |
|---|---|---|
| `.hl` | 일반 강조 | 굵게 (본문색) |
| `.hl-p` | 핵심 포인트 | 굵게 + 브랜드 퍼플 |

어두운/컬러 배경 영역(히어로, About 비주얼, Why Hiionn, CTA, 푸터)에서는
가독성을 위해 자동으로 흰색으로 전환됩니다. 강조를 추가할 때는
`<span class="hl">문구</span>` 형태로 **문장 전체가 아닌 핵심 어구만** 감싸세요.

## 미니프로그램 데모

`#demo` 섹션은 WeChat 미니프로그램 고객 경험을 브라우저에서 시연하는
클릭형 데모입니다. **예시 데이터로만 동작하며 실제 예약·결제·AI API와
연동되지 않습니다.** 데모에 쓰인 병원·진료실·강의실 사진은 AI로 생성한
일반 이미지로, 특정 병원의 실제 전경이 아닙니다.

## 이미지 교체 안내

`images/content-*.jpg`, `online-content.jpg`는 **예시 목적**의 이미지입니다.
실제 대외 공개 시에는 자체 촬영 또는 저작권이 확보된 이미지로 교체하세요.
**같은 파일명으로 `images/` 안의 파일만 바꿔치기하면 코드 수정은 필요 없습니다.**
(단, 위에 설명한 반응형 축소본도 함께 교체해야 합니다.)

## 문의

(주)아크로모빌리티 · hiionn@acromobility.com · TEL. +82-2-6952-1617
