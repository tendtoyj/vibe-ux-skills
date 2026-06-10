# Vibe UX Skills

바이브 코딩으로 **신규 서비스(앱/웹)를 처음부터 기획**하기 위한 Claude Code / Codex 스킬 모음입니다. 아이디어 한 줄에서 시작해 `docs/` 폴더에 기획 문서를 단계별로 쌓아 올리고, 마지막에 하나의 PRD로 묶습니다.

## 기획 플로우

| 순서 | 스킬 | 입력 | 산출물 |
|------|------|------|--------|
| 1 | `brainstorming-idea` | (대화) | `docs/idea.md` |
| 2 | `benchmark-research` | `idea.md` | `docs/benchmark.md` (+ `docs/images/`) |
| 3 | `userflow-generator` | `idea.md`, `benchmark.md` | `docs/userflow.md` |
| 4 | `brand-voice` | `idea.md`, `benchmark.md` | `docs/brandvoice.md` |
| 5 | `design-brandfit` | `DESIGN.md`, `brandvoice.md` | 브랜드화된 `DESIGN.md` |
| 6 | `to-prd` | 위 네 문서 | `docs/PRD.md` |

각 단계는 독립적으로도 쓸 수 있지만, 순서대로 진행하면 앞 단계 산출물이 뒤 단계의 입력이 됩니다.

## 설치

### Claude Code

```
/plugin marketplace add tendtoyj/vibe-ux-skills
/plugin install vibe-ux@vibe-ux-skills
```

### Codex

Codex CLI에서 marketplace를 추가한 뒤 `/plugins`에서 `vibe-ux`를 설치합니다.

```
codex plugin marketplace add tendtoyj/vibe-ux-skills
codex
/plugins
```

Codex app에서는 Plugins에서 추가된 marketplace를 열고 `Vibe UX`를 설치합니다. 설치 후 새 thread에서 사용하는 것을 권장합니다.

## 사용

Claude Code에서는 스킬이 네임스페이스와 함께 등록됩니다:

```
/vibe-ux:brainstorming-idea
/vibe-ux:benchmark-research
/vibe-ux:userflow-generator
/vibe-ux:brand-voice
/vibe-ux:design-brandfit
/vibe-ux:to-prd
```

Codex에서는 자연어로 요청하거나, `$`로 개별 스킬을 명시 호출할 수 있습니다:

```
$brainstorming-idea
$benchmark-research
$userflow-generator
$brand-voice
$design-brandfit
$to-prd
```

또는 자연어로 "서비스 아이디어 잡아줘", "벤치마크 조사해줘", "PRD로 묶어줘"처럼 말해도 해당 스킬이 트리거됩니다.

## 라이선스

[MIT](./LICENSE)
