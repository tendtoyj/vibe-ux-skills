# Vibe UX Skills

바이브 코딩으로 **신규 서비스(앱/웹)를 처음부터 기획하고 구현**하기 위한 Claude Code / Codex 스킬 모음입니다. 아이디어 한 줄에서 시작해 `docs/` 폴더에 문서를 단계별로 쌓아 올리고, PRD로 묶은 뒤, 로드맵·마일스톤 계획을 거쳐 실제 코드 구현까지 이어집니다.

이 마켓플레이스에는 두 개의 플러그인이 있습니다:

- **`vibe-ux`** — 기획 플로우 (아이디어 → PRD)
- **`vibe-build`** — 구현 플로우 (PRD → 코드)

## 기획 플로우 (vibe-ux)

| 순서 | 스킬 | 입력 | 산출물 |
|------|------|------|--------|
| 1 | `brainstorming-idea` | (대화) | `docs/idea.md` |
| 2 | `benchmark-research` | `idea.md` | `docs/benchmark.md` (+ `docs/images/`) |
| 3 | `userflow-generator` | `idea.md`, `benchmark.md` | `docs/userflow.md` |
| 4 | `brand-voice` | `idea.md`, `benchmark.md` | `docs/brandvoice.md` |
| 5 | `design-brandfit` | `DESIGN.md`, `brandvoice.md` | 브랜드화된 `DESIGN.md` |
| 6 | `to-prd` | 위 네 문서 | `docs/PRD.md` |

## 구현 플로우 (vibe-build)

`vibe-ux`로 만든 `docs/PRD.md`(또는 직접 작성한 PRD)에서 이어집니다.

| 순서 | 스킬 | 입력 | 산출물 |
|------|------|------|--------|
| 1 | `roadmap` | `PRD.md` | `docs/ROADMAP.md` (프론트 목업 우선 마일스톤) |
| 2 | `plan` | `PRD.md`, `ROADMAP.md` | `docs/milestones/M*/plan.md`, `tasks.md` |
| 3 | `build` | 마일스톤의 `plan.md`, `tasks.md` | 구현된 코드 (예: `/build M1`) |

각 단계는 독립적으로도 쓸 수 있지만, 순서대로 진행하면 앞 단계 산출물이 뒤 단계의 입력이 됩니다.

## 설치

### Claude Code

```
/plugin marketplace add tendtoyj/vibe-ux-skills
/plugin install vibe-ux@vibe-ux-skills
/plugin install vibe-build@vibe-ux-skills
```

### Codex

Codex CLI에서 marketplace를 추가한 뒤 `/plugins`에서 `vibe-ux` / `vibe-build`를 설치합니다.

```
codex plugin marketplace add tendtoyj/vibe-ux-skills
codex
/plugins
```

Codex app에서는 Plugins에서 추가된 marketplace를 열고 `Vibe UX` / `Vibe Build`를 설치합니다. 설치 후 새 thread에서 사용하는 것을 권장합니다.

## 사용

Claude Code에서는 스킬이 네임스페이스와 함께 등록됩니다:

```
# 기획
/vibe-ux:brainstorming-idea
/vibe-ux:benchmark-research
/vibe-ux:userflow-generator
/vibe-ux:brand-voice
/vibe-ux:design-brandfit
/vibe-ux:to-prd

# 구현
/vibe-build:roadmap
/vibe-build:plan
/vibe-build:build
```

Codex에서는 자연어로 요청하거나, `$`로 개별 스킬을 명시 호출할 수 있습니다:

```
$brainstorming-idea
$benchmark-research
$userflow-generator
$brand-voice
$design-brandfit
$to-prd
$roadmap
$plan
$build
```

또는 자연어로 "서비스 아이디어 잡아줘", "벤치마크 조사해줘", "PRD로 묶어줘", "로드맵 짜줘", "M1 구현해줘"처럼 말해도 해당 스킬이 트리거됩니다.

## 라이선스

[MIT](./LICENSE)
