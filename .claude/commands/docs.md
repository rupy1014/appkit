---
description: Create documentation for existing implemented features from a natural language description.
---

## User Input

```text
$ARGUMENTS
```

You **MUST** consider the user input before proceeding (if not empty).

## Outline

The text the user typed after `/speckit.document` in the triggering message **is** the feature description (summarized by the user). Assume you always have it available in this conversation even if `$ARGUMENTS` appears literally below. Do not ask the user to repeat it unless they provided an empty command.

Given that feature description, do this:

1. **Generate a concise document name** (2-4 words):
   - Analyze the feature description and extract the most meaningful keywords
   - Create a 2-4 word name that captures the essence of the feature
   - Use noun format when possible (e.g., "cart-feature", "payment-system", "user-authentication")
   - Preserve technical terms and acronyms (OAuth2, API, JWT, etc.)
   - Keep it concise but descriptive enough to understand the feature at a glance
   - Examples:
     - "장바구니 기능입니다" → "cart-feature"
     - "결제 시스템 구현" → "payment-system"
     - "사용자 인증 OAuth2" → "oauth2-authentication"
     - "리뷰 포인트 시스템" → "review-points-system"

2. **Determine output location** (NO script execution, NO branch creation):
   - Create docs directory if needed: `docs/` or `.specify/docs/`
   - Generate filename: `[document-name].md` (e.g., `cart-feature.md`)
   - Full path example: `docs/cart-feature.md`

3. Load `.specify/templates/docs-template.md` to understand required sections.

4. Follow this execution flow:

    1. Parse user description from Input
       If empty: ERROR "No feature description provided"
    2. Extract key information from description:
       - Feature overview and purpose
       - Business policies mentioned
       - Main logic flows
       - Implemented features
       - API endpoints (if mentioned)
       - Known issues or improvements
       - Related files (if mentioned)
    3. For unclear aspects:
       - Make informed guesses based on context and industry standards
       - Only mark with [NEEDS CLARIFICATION: specific question] if:
         - The choice significantly impacts documentation completeness
         - Multiple reasonable interpretations exist with different implications
         - No reasonable default exists
       - **LIMIT: Maximum 3 [NEEDS CLARIFICATION] markers total**
       - Prioritize clarifications by impact: business policy > logic flow > feature details
    4. Fill all mandatory sections:
       - Overview
       - Business Policy (policies with reasons)
       - Main Logic
       - Feature List (completed and incomplete)
       - API List (if applicable)
       - Issues/Improvements
       - Related Files
    5. Return: SUCCESS (documentation ready)

5. Write the documentation to the determined file path using the template structure, replacing placeholders with concrete details derived from the feature description while preserving section order and headings.

6. **Documentation Quality Validation**: After writing the initial docs, validate it against quality criteria:

   a. **Create Documentation Quality Checklist**: Generate a checklist file at `docs/checklists/[document-name]-quality.md` (or `.specify/docs/checklists/[document-name]-quality.md`) with these validation items:

      ```markdown
      # Documentation Quality Checklist: [FEATURE NAME]

      **Purpose**: Validate documentation completeness and quality
      **Created**: [DATE]
      **Feature**: [Link to docs.md]

      ## Content Completeness

      - [ ] Overview clearly explains the feature purpose
      - [ ] All business policies documented with reasons
      - [ ] Main logic flows are described
      - [ ] Feature list includes both completed and incomplete items
      - [ ] API list is complete (if feature has APIs)
      - [ ] Issues/improvements are identified
      - [ ] Related files are listed

      ## Policy Documentation

      - [ ] No [NEEDS CLARIFICATION] markers remain
      - [ ] Each policy includes the reason/background
      - [ ] Policies are clear and unambiguous
      - [ ] Missing policies are identified in Issues/Improvements

      ## Documentation Quality

      - [ ] Written in clear, understandable language
      - [ ] Technical terms are used appropriately
      - [ ] Examples are provided where helpful
      - [ ] Document is well-structured and easy to navigate

      ## Notes

      - Items marked incomplete require docs updates or clarification
      ```

   b. **Run Validation Check**: Review the docs against each checklist item:
      - For each item, determine if it passes or fails
      - Document specific issues found (quote relevant sections)

   c. **Handle Validation Results**:

      - **If all items pass**: Mark checklist complete and proceed to step 7

      - **If items fail (excluding [NEEDS CLARIFICATION])**:
        1. List the failing items and specific issues
        2. Update the docs to address each issue
        3. Re-run validation until all items pass (max 3 iterations)
        4. If still failing after 3 iterations, document remaining issues in checklist notes and warn user

      - **If [NEEDS CLARIFICATION] markers remain**:
        1. Extract all [NEEDS CLARIFICATION: ...] markers from the docs
        2. **LIMIT CHECK**: If more than 3 markers exist, keep only the 3 most critical (by policy/logic/feature impact) and make informed guesses for the rest
        3. **CRITICAL - Korean Communication**: Present all questions in Korean to the user
        4. For each clarification needed (max 3), present options to user in this format:

           ```markdown
           ## 질문 [N]: [주제]

           **문맥**: [문서의 관련 섹션 인용]

           **알아야 할 내용**: [NEEDS CLARIFICATION 마커의 구체적 질문]

           **제안 답변**:

           | 옵션 | 답변 | 문서화 영향 |
           |------|------|-------------|
           | A | [첫 번째 제안 답변] | [문서화에 미치는 영향] |
           | B | [두 번째 제안 답변] | [문서화에 미치는 영향] |
           | C | [세 번째 제안 답변] | [문서화에 미치는 영향] |
           | 직접입력 | 직접 답변 제공 | [사용자가 직접 입력하는 방법 설명] |

           **선택**: _[사용자 응답 대기]_
           ```

        5. **CRITICAL - Table Formatting**: Ensure markdown tables are properly formatted:
           - Use consistent spacing with pipes aligned
           - Each cell should have spaces around content: `| Content |` not `|Content|`
           - Header separator must have at least 3 dashes: `|--------|`
           - Test that the table renders correctly in markdown preview
        6. Number questions sequentially in Korean (질문1, 질문2, 질문3 - max 3 total)
        7. Present all questions together before waiting for responses
        8. Wait for user to respond with their choices for all questions (e.g., "질문1: A, 질문2: 직접입력 - [상세내용], 질문3: B")
        9. Update the docs by replacing each [NEEDS CLARIFICATION] marker with the user's selected or provided answer
        10. Re-run validation after all clarifications are resolved

   d. **Update Checklist**: After each validation iteration, update the checklist file with current pass/fail status

7. Report completion with document file path, checklist results, and any identified issues/improvements.

**NOTE:** This command does NOT create branches or run scripts - it only creates documentation files.

## General Guidelines

## Quick Guidelines

- Focus on documenting **WHAT is implemented**, **WHY (business reasons)**, and **HOW (main logic)**.
- Include both completed and incomplete features.
- Identify issues and improvements discovered during documentation.
- Written for both technical and non-technical stakeholders.

### Section Requirements

- **Mandatory sections**: Must be completed for every feature
- **Optional sections**: Include only when relevant to the feature (e.g., API List)
- When a section doesn't apply, remove it entirely (don't leave as "N/A")

### For AI Generation

When creating this documentation from a user prompt:

1. **Make informed guesses**: Use context, industry standards, and common patterns to fill gaps
2. **Document what's known**: Focus on information explicitly provided by the user
3. **Limit clarifications**: Maximum 3 [NEEDS CLARIFICATION] markers - use only for critical information that:
   - Significantly impacts documentation completeness
   - Has multiple reasonable interpretations with different implications
   - Lacks any reasonable default
4. **Prioritize clarifications**: business policy > logic flow > feature details
5. **Think practically**: Document what exists, flag what's missing in Issues/Improvements
6. **Common areas needing clarification** (only if no reasonable default exists):
   - Business policy reasons (why this implementation was chosen)
   - Missing or unclear logic flows
   - Incomplete feature status (implemented vs planned)

**Examples of reasonable defaults** (don't ask about these):

- Standard CRUD operations: If basic endpoints are mentioned, assume standard patterns
- Common business policies: Industry-standard practices unless specified otherwise
- File organization: Standard Rails/project conventions unless specified
- Error handling: Standard error responses unless specified

### Documentation Structure Guidelines

Documentation should be:

1. **Clear**: Use simple language, avoid jargon unless necessary
2. **Complete**: All mandatory sections filled appropriately
3. **Accurate**: Based on user's description, not assumptions
4. **Actionable**: Issues/improvements are specific and practical

**Good examples**:

- "재고 차감 시점: 장바구니 추가 시 (이유: 한정 수량 선점 방지)"
- "만료 정책: 30일 후 자동 만료 (이유: 데이터 누적 방지)"
- "[ ] [P1] 재고 복구 배치 작업 미구현 (현재 재고가 복구되지 않음)"

**Bad examples**:

- "정책 있음" (not specific)
- "잘 작동함" (no business reason)
- "개선 필요" (not actionable)
