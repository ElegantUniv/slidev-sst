---
layout: cover
---

# Slidev 레이아웃(Layout) 활용

---
layout: default
---

# 레이아웃이란?

슬라이드 각각의 모양을 결정하는 틀이다. 슬라이드 상단 frontmatter의 `layout` 속성으로 지정한다.

```md
---
layout: cover
---

# 제목 슬라이드
```

지정하지 않으면 `default` 레이아웃이 적용된다.

---
layout: default
---

# 기본 제공 레이아웃 목록

| 레이아웃 | 용도 |
|---|---|
| `cover` | 발표 시작 표지 슬라이드 |
| `default` | 일반 콘텐츠 슬라이드 |
| `center` | 내용을 화면 중앙에 배치 |
| `section` | 섹션 구분 슬라이드 |
| `two-cols` | 좌우 두 열로 나누어 배치 |
| `image-right` | 오른쪽에 이미지, 왼쪽에 텍스트 |
| `image-left` | 왼쪽에 이미지, 오른쪽에 텍스트 |
| `fact` | 숫자·핵심 사실 강조 |
| `quote` | 인용문 강조 |
| `end` | 발표 마무리 슬라이드 |

---
layout: default
---

# `cover` / `section` / `end`

발표의 구조를 잡는 데 사용한다.

```md
---
layout: cover
---
# 발표 제목
발표자 이름

---
layout: section
---
# 2장. 주요 기능

---
layout: end
---
# 감사합니다
```

---
layout: default
---

# `center`

내용을 슬라이드 정중앙에 배치할 때 사용한다.

```md
---
layout: center
---

# 한 줄 메시지를 강조할 때 유용하다
```

---
layout: default
---

# `two-cols`

`::left::` / `::right::` 슬롯으로 좌우 열을 나눈다.

```md
---
layout: two-cols
---

::left::
## 왼쪽
- 항목 A
- 항목 B

::right::
## 오른쪽
- 항목 C
- 항목 D
```

---
layout: default
---

# `image-right` / `image-left`

`image` 속성으로 이미지 경로를 지정하고, 슬라이드 본문이 반대쪽에 표시된다.

```md
---
layout: image-right
image: /images/welcome-to-slidev.png
---

## 이미지 옆에 설명 작성
이미지는 오른쪽, 텍스트는 왼쪽에 배치된다.
```

`image-left`는 이미지와 텍스트의 위치가 반대이다.

---
layout: default
---

# `fact` / `quote`

핵심 수치나 인용문을 돋보이게 할 때 사용한다.

```md
---
layout: fact
---

## 52,000+
GitHub Stars

---
layout: quote
---

"간결한 마크다운으로 세련된 슬라이드를."

— Slidev
```
