---
name: roadmap
description: docs/PRD.md를 바탕으로 프론트엔드 목업 우선 마일스톤 로드맵을 작성합니다. PRD가 준비된 뒤 구현을 여러 마일스톤과 버티컬 슬라이스로 나누고 싶을 때 사용합니다.
---

# Overview

이 스킬은 `docs/PRD.md`를 읽고, PRD의 Functional Requirements를 충족하기 위한 단계별 구현 로드맵을 작성한다.

로드맵의 핵심 목적은 바로 기능 구현으로 들어가지 않고, 먼저 프론트엔드 목업 품질을 충분히 끌어올린 뒤 실제 기능 구현을 버티컬 슬라이스 단위로 진행하게 만드는 것이다.

최종 산출물은 `docs/ROADMAP.md`다. 문서는 한국어로 작성한다. 필요한 경우 섹션 제목은 영어를 사용할 수 있지만, 본문 설명은 한국어로 작성한다.

# Inputs

반드시 다음 파일을 읽는다.

1. `docs/PRD.md`
2. `docs/DESIGN.md`

선택적으로, 있으면 읽는다.

1. `docs/brandvoice.md`
2. `docs/benchmark.md`
3. `docs/userflow.md`
4. `docs/idea.md`

`docs/PRD.md`가 없거나 비어 있으면 로드맵을 작성하지 말고, 먼저 PRD가 필요하다고 보고한다.

`docs/DESIGN.md`가 없거나 비어 있으면 로드맵을 작성하지 말고, 첫 번째 마일스톤의 기준이 될 디자인 문서가 필요하다고 보고한다.

# Output

`docs/ROADMAP.md`를 작성한다.

로드맵에는 반드시 다음 내용을 포함한다.

1. 기술 스택
2. 마일스톤 목록
3. 각 마일스톤의 목표
4. 각 마일스톤이 충족하는 Functional Requirements
5. 각 마일스톤의 범위와 제외 범위
6. 각 마일스톤의 완료 기준
7. 마일스톤 간 의존성

이 스킬은 태스크 파일을 만들지 않는다. 각 마일스톤은 이후 별도의 계획/태스크 분리 스킬에서 태스크 덩어리로 쪼갤 수 있을 만큼 명확하게 정의한다.

# Tech Stack Rules

사용자가 명시적으로 다른 기술 스택을 요구하지 않았다면 기본 기술 스택은 다음으로 정한다.

- TypeScript
- Next.js
- Tailwind CSS
- Supabase

기술 스택은 로드맵의 첫 부분에 명시한다.

PRD나 기존 문서에 다른 기술 제약이 명시되어 있으면 그 내용을 우선한다. 단, 명시적 근거 없이 임의로 새로운 프레임워크, UI 라이브러리, 백엔드, 데이터베이스를 추가하지 않는다.

# Milestone Rules

## Milestone 1: Frontend Mockup

첫 번째 마일스톤은 반드시 `docs/DESIGN.md`를 기반으로 한 프론트엔드 목업이다.

이 마일스톤은 실제 기능, DB, 인증, 백엔드 로직 구현이 목적이 아니다. 목적은 hi-fidelity working prototype에 가까운 프론트엔드 목업을 만들고, 디자인 토큰과 UI 컴포넌트의 품질을 높이는 것이다.

Milestone 1에는 다음을 포함한다.

- `docs/DESIGN.md`의 시각 방향, 레이아웃, 톤, 컴포넌트 원칙 반영
- PRD의 핵심 사용자 시나리오를 눈으로 확인할 수 있는 주요 화면 구성
- 실제 데이터 대신 더미 데이터 또는 정적 상태 사용
- 주요 상태 표현: 기본, 빈 상태, 로딩 상태, 오류 상태, 선택/활성 상태
- 디자인 토큰: 색상, 타이포그래피, 간격, radius, shadow, motion 원칙
- 재사용 가능한 UI 컴포넌트 후보 정의
- 모바일/데스크톱 등 PRD나 디자인 문서가 요구하는 주요 반응형 기준

Milestone 1의 완료 기준은 기능 동작이 아니라, 사용자가 핵심 흐름을 시각적으로 이해하고 디자인 품질을 판단할 수 있는 수준이어야 한다.

## Milestone 2+

두 번째 마일스톤부터 실제 기능 구현을 시작한다. 필요한 경우 DB, 백엔드 로직, 인증, 외부 연동, 상태 관리, 저장 로직을 포함한다.

두 번째 마일스톤부터는 반드시 버티컬 슬라이스로 정의한다. 각 마일스톤은 가능한 한 사용자가 실제로 완료할 수 있는 하나의 가치 흐름을 끝까지 포함해야 한다.

좋은 버티컬 슬라이스:

- 하나의 사용자 목표를 end-to-end로 완성한다.
- 필요한 UI, 상태, 데이터, API/백엔드, 검증, 테스트 범위를 함께 포함한다.
- 완료되면 독립적으로 데모하거나 검증할 수 있다.
- PRD의 Functional Requirements 일부를 명확히 충족한다.
- 다른 마일스톤에 비해 의존성이 낮거나, 의존성이 있으면 명확히 적는다.

나쁜 슬라이스:

- “DB 전체 만들기”, “API 전체 만들기”, “UI 전체 만들기”처럼 레이어별로만 나눈다.
- 사용자가 체감할 수 있는 완성 흐름 없이 내부 구조만 만든다.
- 여러 사용자 목표를 한 마일스톤에 과하게 묶는다.
- 완료 기준이 “구현 완료”, “잘 동작”처럼 검증 불가능하다.
- 특정 파일이나 코드 작업 목록 수준으로 너무 잘게 쪼개져 있다.

# Process

1. `docs/PRD.md`에서 Functional Requirements, User Scenarios, Success Criteria, Edge Cases, Assumptions를 파악한다.
2. `docs/DESIGN.md`에서 첫 번째 마일스톤의 프론트엔드 목업 기준을 파악한다.
3. 명시적 기술 스택 요구가 있는지 확인한다. 없으면 기본 스택을 TypeScript + Next.js + Tailwind CSS + Supabase로 둔다.
4. 모든 Functional Requirements를 빠짐없이 커버할 수 있도록 마일스톤을 큼직하게 나눈다.
5. 첫 번째 마일스톤은 프론트엔드 목업과 디자인 토큰/UI 컴포넌트 품질 개선에 집중하도록 정의한다.
6. 두 번째 마일스톤부터는 PRD의 사용자 가치 흐름 기준으로 버티컬 슬라이스를 정의한다.
7. 각 마일스톤마다 포함 범위, 제외 범위, 완료 기준, 관련 Functional Requirements, 의존성을 적는다.
8. 어떤 Functional Requirement가 어느 마일스톤에서 충족되는지 추적 가능한 표를 작성한다.
9. `docs/ROADMAP.md`에 최종 로드맵을 작성한다.

# Roadmap Structure

`docs/ROADMAP.md`는 아래 구조를 따른다.

```markdown
# Roadmap

## Tech Stack

## Milestone Overview

## Milestone 1 - Frontend Mockup

### Goal
### Scope
### Out of Scope
### Design Focus
### Functional Requirements Covered
### Completion Criteria
### Dependencies

## Milestone 2 - [Vertical Slice Name]

### Goal
### User Value
### Scope
### Out of Scope
### Functional Requirements Covered
### Completion Criteria
### Dependencies

## Milestone 3 - [Vertical Slice Name]

...

## Requirement Coverage

## Notes
```

마일스톤 수는 PRD 크기에 맞게 정한다. 단, Milestone 1은 항상 `Frontend Mockup`이어야 한다.

# Writing Rules

- 로드맵 본문은 한국어로 작성한다.
- 로드맵은 태스크 목록이 아니라 마일스톤 수준의 구현 전략이다.
- 각 마일스톤은 나중에 태스크로 쪼갤 수 있을 만큼 충분히 구체적이어야 한다.
- Milestone 1에는 실제 Supabase 연동, 실제 인증, 실제 DB 저장, 운영 백엔드 구현을 넣지 않는다. 필요한 경우 더미 데이터와 목업 상태로 표현한다.
- Milestone 2부터는 프론트엔드만 따로, 백엔드만 따로, DB만 따로 나누지 않는다. 사용자 가치가 완결되는 버티컬 슬라이스로 나눈다.
- 모든 Functional Requirements는 최소 하나의 마일스톤에 매핑되어야 한다.
- 한 마일스톤이 너무 커지면 사용자 가치 기준으로 더 작게 나눈다.
- 한 마일스톤이 너무 작아 독립 검증이 어렵다면 인접 흐름과 합친다.
- 구현 세부 파일 목록이나 세부 태스크는 쓰지 않는다. 그것은 다음 단계의 planning/task 스킬에서 다룬다.
- PRD와 DESIGN 문서에 근거가 없는 기능을 임의로 추가하지 않는다. 필요한 추론은 `Notes`에 가정으로 분리한다.

# Final Response

작업을 마치면 `docs/ROADMAP.md`를 작성했다고 간단히 보고하고, 마일스톤 개수와 Milestone 1의 목적, Milestone 2 이후의 버티컬 슬라이스 구성을 요약한다.
