---
layout: cover
---

# Slidev 테마(Theme) 활용

---
layout: default
---

# 테마란?

테마는 슬라이드 전체의 폰트·색상·레이아웃 스타일을 일괄 적용하는 패키지다.

`slides.md` 최상단 frontmatter의 `theme` 속성 하나로 전환한다.

```md
---
theme: seriph
---
```

---
layout: default
---

# 내가 쓰는 테마

검은색에 흰색 글꼴을 쓰는 간단한 테마는 다음과 같다.

```md
---
theme: default
# colorSchema: dark
# background: https://cover.sli.dev
class: text-center
highlighter: shiki
# lineNumbers: true
title: Welcome to Slidev
drawings:
  persist: false
transition: fade
css: unocss
mdc: true
---
```

---
layout: default
---

# 공식 테마 목록

Slidev가 공식으로 제공하는 테마들이다.

| 테마 이름 | 패키지 |
|---|---|
| `default` | `@slidev/theme-default` |
| `seriph` | `@slidev/theme-seriph` |
| `apple-basic` | `@slidev/theme-apple-basic` |
| `bricks` | `@slidev/theme-bricks` |
| `penguin` | `@slidev/theme-penguin` |
| `shibainu` | `@slidev/theme-shibainu` |

전체 목록은 [Slidev 테마 갤러리](https://sli.dev/resources/theme-gallery)에서 확인할 수 있다.

---
layout: default
---

# 테마 설치

`theme`을 변경하면 Slidev가 자동으로 설치를 제안한다.

```
? The theme "@slidev/theme-seriph" was not found in your project,
  do you want to install it now? › Yes
```

또는 직접 설치할 수 있다.

```bash
pnpm add @slidev/theme-seriph
```

이 프로젝트에는 `default`와 `seriph`가 이미 설치되어 있다.

---
layout: default
---

# 커뮤니티 테마 사용

npm에 배포된 커뮤니티 테마도 동일한 방식으로 사용한다.

```bash
# 설치
pnpm add slidev-theme-dracula
```

```md
---
theme: dracula
---
```

패키지명이 `slidev-theme-이름` 형식이면 `이름` 부분만 적어도 된다.

---
layout: default
---

# 테마 옵션

일부 테마는 추가 frontmatter 속성을 지원한다. 대표적인 예시는 다음과 같다.

```md
---
theme: default
colorSchema: dark       # light | dark | auto
background: https://cover.sli.dev   # 표지 배경 이미지
---
```

테마별 지원 옵션은 각 테마의 README에서 확인한다.

---
layout: default
---

# 로컬 테마

패키지 배포 없이 프로젝트 내에 직접 테마를 만들 수 있다.

```bash
slides/
└── theme/
    ├── package.json   # "name": "local" 으로 설정
    └── styles/
        └── index.css
```

```md
---
theme: ./theme
---
```

팀 전용 스타일을 적용하거나 기존 테마를 커스터마이징할 때 유용하다.
