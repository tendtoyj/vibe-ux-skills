---
name: spec
description: docs/idea.md와 docs/userflow.md를 바탕으로 docs/PRD.md를 작성합니다. 아이디어와 사용자 흐름 문서가 준비된 뒤 PRD가 필요할 때 사용합니다.
---

# Overview

이 스킬은 이미 작성된 `docs/idea.md`와 `docs/userflow.md`를 읽고, 제품 요구사항 문서인 `docs/PRD.md`를 작성한다.

사용자 입력을 별도의 feature description으로 취급하지 않는다. 요구사항의 원천은 오직 `docs/idea.md`, `docs/userflow.md`, 그리고 필요 시 현재 저장소에서 확인 가능한 문맥이다.

PRD 문서는 반드시 한국어로 작성한다. 단, PRD의 섹션 제목은 템플릿에 정의된 영어 제목을 그대로 사용한다.

# Inputs

반드시 다음 파일을 먼저 읽는다.

1. `docs/idea.md`
2. `docs/userflow.md`
3. `skills/spec/prd_template.md`

`docs/idea.md` 또는 `docs/userflow.md`가 없거나 비어 있으면 PRD를 작성하지 말고, 어떤 입력 파일이 부족한지 간단히 보고한다.

# Output

최종 산출물은 `docs/PRD.md` 하나다.

`docs/PRD.md`는 `skills/spec/prd_template.md`의 구조를 사용해 작성한다. 섹션은 아래 5개만 포함한다.

1. `User Scenarios`
2. `Functional Requirements`
3. `Success Criteria`
4. `Edge Cases`
5. `Assumptions`

다른 섹션을 추가하지 않는다. 요구사항 품질 체크리스트, 모호성 질문, handoff, 다음 단계 안내는 작성하지 않는다.

# Process

1. `docs/idea.md`에서 제품의 문제, 목표 사용자, 핵심 가치, 주요 기능 후보를 파악한다.
2. `docs/userflow.md`에서 사용자의 주요 흐름, 화면/단계, 상태 변화, 예외 흐름 후보를 파악한다.
3. 두 문서의 내용을 합쳐 구현 방식이 아니라 제품 요구사항 중심으로 정리한다.
4. 불명확한 부분은 사용자에게 질문하지 않는다. 합리적인 기본값을 정하고 `Assumptions`에 명시한다.
5. PRD를 `docs/PRD.md`에 작성한다.

# Writing Rules

- PRD 본문은 한국어로 작성한다.
- 섹션 제목은 템플릿의 영어 제목을 그대로 유지한다.
- 기능 요구사항은 테스트 가능한 문장으로 작성한다.
- 성공 기준은 가능한 한 관찰 가능하고 측정 가능한 조건으로 작성한다.
- 사용자 시나리오는 사용자가 실제로 얻는 가치와 완료 조건이 드러나게 작성한다.
- Edge Cases는 빈 상태, 오류 상태, 중복 입력, 취소/이탈, 권한/접근 제한, 데이터 부족 같은 실패 모드를 우선 검토한다.
- 구현 기술, 파일 경로, 내부 아키텍처, 라이브러리 선택은 PRD에 포함하지 않는다. 단, 입력 문서가 명시한 제품 제약은 요구사항이나 가정에 반영한다.
- 원문에 없는 기능을 과도하게 추가하지 않는다. 필요한 추론은 `Assumptions`에 분리한다.

# Final Response

작업을 마치면 `docs/PRD.md`를 작성했다고 간단히 보고하고, 핵심적으로 채운 섹션만 요약한다.
