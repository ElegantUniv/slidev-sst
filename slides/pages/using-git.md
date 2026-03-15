---
layout: cover
---

# git와 함께 활용하기

- reference: 
["Slidev for Tech Talks" by Martin Brochhaus | PUGS Meetup May 2023 @ Red Hat](https://youtu.be/gsWCVPsoClw)


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
    - `Project name:`에서 프로젝트명은 `slides`로 통일하자.
    - `Choose the package manager`에서는 pnpm을 고르도록 하자.
```shell
pwd # /dev/source/repos/slidev-sst
pnpm create slidev
...
√ Project name: ... slides
...
? Choose the package manager
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

- 프로젝트 폴더는 `slides` 디렉토리이며, 실질적인 작업 디렉토리가 된다.
- `slides` 디렉토리로 이동한다. 

```shell
cd slides
pwd # /dev/source/repos/slidev-sst/slides
```

---
layout: default
---

# 슬라이드 내용 편집 및 반영

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




---
layout: default
---

# Slidev 프로젝트 지속적인 개발

다른 컴퓨터에서 자신이 만든 slidev 프로젝트를 클로닝해 개발할 경우

- `slides` 디렉토리에서 `pnpm run dev`를 실행하여 계속적인 개발 진행이 가능하다. 

```shell
pwd # /dev/source/repos/slidev-sst/slides
pnpm run dev
```

⚠️ 만일 아래와 같은 에러가 뜬다면 `node_modules`가 누락된 경우이다.
- 프로젝트 설정 파일(`package.json`)은 있지만, 실제 실행 파일들이 있는 `node_modules` 폴더가 없는 경우이다.

```bash
'slidev' is not recognized as an internal or external command, operable program or batch file.
 ELIFECYCLE  Command failed with exit code 1.
 WARN   Local package.json exists, but node_modules missing, did you mean to install?
```

- 프로젝트 폴더에서 인스톨 명령을 수행하자.

```bash
pnpm install
```
