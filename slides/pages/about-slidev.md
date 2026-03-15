---
layout: cover
---

# Slidev 소개

[Slidev 홈페이지](https://sli.dev/)

---
layout: default
---

# Slidev 소개

https://elegantuniv.github.io/slidev-sample

<img src="/images/welcome-to-slidev.png" class="w-[700px] m-auto mt-4" />


---
layout: default
---

# Slidev 설치하기

- 먼저 [Node.js](https://nodejs.org/ko/download)를 설치한다.
- [Slidev 홈페이지](https://sli.dev/)의 [Getting Started](https://sli.dev/guide/)의 Create Locally에서 소개한 바와 같이 slidev 프로젝트를 만들 수 있다.

## slidev 프로젝트 만들기

Node.js command prompt를 띄운 다음, 아래의 명령어를 기입하자.

```bash
npm i -g pnpm

pnpm create slidev
```

---
layout: default
---

# Slidev 프로젝트 생성

아래와 같은 화면이 뜨면서 생성할 프로젝트 이름을 CLI로 받기를 기다린다.

```sh
  ●■▲
  Slidev Creator  v52.14.1

√ Project name: ... 
```

다음은 프로젝트 이름을 `slides`로 설정한 예이다.

```sh
√ Project name: ... slides
  Scaffolding project in slides ...
  Done.

√ Install and start it now? ... yes
√ Choose the package manager » pnpm
Packages: +621
```

`slides`라는 폴더가 만들어 지고, 해당 부분에 기본값으로 구성된 프로젝트가 만들어진다.

---
layout: default
---

# Slidev 프로젝트 실행

프로젝트 폴더로 가서 아래 명령어를 수행하도록 하자.

```bash
pnpm run dev 
```


