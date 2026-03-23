---
layout: cover
---

# AI와 함께 Slidev 활용하기

Claude Code 스킬(Skill) 설치 및 활용

---
layout: default
---

# Claude Code란?

[Claude Code](https://claude.ai/code)는 Anthropic이 만든 AI 코딩 도우미 CLI 도구다.

## 설치
Claude Code Docs의 [빠른 시작](https://code.claude.com/docs/ko/quickstart)을 보고 Claude Code를 설치한다.

```bash
# 프로젝트 폴더에서 실행
claude
```

터미널에서 대화하듯 지시하면 파일 읽기·수정·명령 실행까지 자율적으로 수행한다.

---
layout: default
---

# 스킬(Skill)이란?

스킬은 Claude Code에 새로운 능력과 도메인 지식을 추가하는 확장 기능이다.

- `SKILL.md` 파일 하나로 구성된 가벼운 확장
- 슬래시 명령어(`/스킬명`)로 직접 호출하거나, Claude가 문맥에 맞게 자동 호출
- 개인·프로젝트·조직 범위로 적용 범위를 나눌 수 있음

```
~/.claude/skills/slidev/SKILL.md   ← 개인 범위 (모든 프로젝트에 적용)
.claude/skills/slidev/SKILL.md     ← 프로젝트 범위 (이 프로젝트에만 적용)
```

Slidev는 Claude Code 스킬을 공식적으로 제공하고 있다. [이곳]을 참고해서 다음과 같이 설치하면 된다.

```bash
npx skills add slidevjs/slidev
```

---
layout: default
---

# AI와 함께하는 슬라이드 제작 흐름

```txt
1. claude 실행      # 프로젝트 폴더에서 Claude Code 시작
      ↓
2. /init            # 현재 디렉토리를 참고해서 CLAUDE.md 초기화     
      ↓
3. Slidev presentation을 만들어 Claude에게 달라고 요청
      ↓
4. 결과 확인         # pnpm dev 로 브라우저에서 실시간 확인
      ↓
5. 추가 수정 요청     # 대화 이어가며 반복 개선
```

마크다운 문법을 몰라도 자연어 지시만으로 슬라이드를 만들 수 있다.
