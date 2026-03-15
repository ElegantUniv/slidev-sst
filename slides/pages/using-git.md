---
layout: cover
---

# git와 함께 활용하기

---
layout: default
---

# `github.com`에 원격 리포지토리 생성

```shell
예) https://github.com/ElegantUniv/slidev-sst.git
```

<img src="/images/github-slidev-sst.png" class="w-[350px] m-auto mt-4" />

---
layout: default
---

# 클로닝을 통해 로컬 리포지토리에 저장

```shell
pwd # /dev/source/repos
git clone https://github.com/ElegantUniv/slidev-sst.git
cd slidev-sst
pwd # /dev/source/repos/slidev-sst
```

---
layout: default
---

# `slidev` 프로젝트 만들기 
- `pnpm create slidev` 명령으로 프로젝트를 생성한다.
- 관리의 편의성을 위해, 프로젝트 이름은 `slides`로 통일하자.

```shell
pwd # /dev/source/repos/slidev-sst
pnpm create slidev
...
√ Project name: ... slides
...
```

---
layout: default
---

# `slidev` 프로젝트 만들기 

- 프로젝트를 생성하면, 다음과 같은 디렉토리 구조가 된다


```shell
slidev-sst/
├── .git
├── slides
└── REAME.md 
```

- `slides` 디렉토리가 실질적인 작업디렉토리이므로 `slides` 디렉토리로 이동한다. 

```shell
cd slides
pwd # /dev/source/repos/slidev-sst/slides
```

- 이후 `slides` 디렉토리에서 `pnpm run dev`를 실행하여 계속적인 개발 진행이 가능하다. 

```shell
pwd # /dev/source/repos/slidev-sst/slides
pnpm run dev
```

---
layout: default
---

# `slides` 폴더를 작업디렉토리로  편집된 내용 반영

- visual studio code 등의 편집기를 통해 `slides.md` 파일을 편집한다.

```shell
pwd # /dev/source/repos/slidev-sst/slides
code . # visual studio code 등을 통해 slides.md 파일 편집
```

- 변경된 내용을 commit 하도록 하자.

```shell
git add -A
git commit -m "Initial commit"
git push -u origin main
```

---
layout: default
---

# `github.com`을 통한 퍼블리쉬

- `slides/package.json` 의 `build` 옵션을 다음과 같이 변경한다.

```json
  "build": "slidev build --base /slidev-sst",
```

- `build`하여 만들어진 `./dist` 폴더를 `../docs/` 폴더로 이동시키고 원격 저장소에 반영한다.

```sh
pwd # /dev/source/repos/slidev-sst/slides
pnpm run build
mv ./dist ../docs

git add -A
git commit -m "docs commit"
git push -u origin main
```

---
layout: default
---

# `github.com`을 통한 퍼블리쉬

- 해당 프로젝트의 > Settings > Pages 방문
`https://github.com/ElegantUniv/slidev-sst/settings/pages`
- Build and deployment > Source > Deploy from a branch
- Branch > main > /docs > `Save` 버튼 클릭

<img src="/images/github-slidev-sst-settings-pages.png" class="w-[400px] m-auto mt-4" />


---
layout: default
---

# 브라우저로 접근

약 10분 정도 후에, 다음 페이지 방문하면 슬라이드가 웹으로 뜬다.

https://elegantuniv.github.io/slidev-sst



