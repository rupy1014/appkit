---
description: 기능 구체화 - 각 기능을 사용자 가치 관점에서 구체화
---

## User Input

```text
$ARGUMENTS
```

User input **must** be considered.

## Overview

**This is Step 2 of the logical thinking 7-step workflow**:

```
논리적 사고 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?) ← YOU ARE HERE
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

User inputs in format: `/appkit.spec <spec-id> "<natural language description>"`

Examples:
- `/appkit.spec 003-booking "search and book courts from main screen"`
- `/appkit.spec 003-booking "time deal 30% discount, within 2 days of booking date"`
- `/appkit.spec 004-promotion "no duplicate coupon use, max 40% discount"`

**Core Concepts**:
- **Incremental detailing**: Don't write everything at once
- **Preserve existing content**: Previous content + new content added
- **Natural language input**: User inputs comfortably in natural language

**Note**: As you detail multiple specs, concepts may overlap or conflict. This is expected! The `/appkit.merge` command (Step 3) will consolidate these later.

## Execution Flow

### 1. Input Parsing

**Format**: `/appkit.spec <spec-id> "<natural language description>"`

**Parsing**:
```
Example: /appkit.spec 003-booking "searchable from main screen"

Extract:
- spec-id: 003-booking
- natural language description: "searchable from main screen"
```

**Validation**:
- Error if spec-id is empty
- Error if natural language description is empty

### 2. Script Execution

**Script**: `.app/scripts/get-spec-path.sh --json --spec-id "003-booking"`

**Example Output**:
```json
{
  "SPEC_FILE": "docs/appkit/specs/003-booking/spec.md",
  "SPEC_DIR": "docs/appkit/specs/003-booking"
}
```

**Error Handling**:
- If spec directory doesn't exist: "Spec 003-booking does not exist. Run /appkit.new first."

### 3. Load Existing Spec

**Read File**: `docs/appkit/specs/003-booking/spec.md`

**Check Status**:
1. **Empty template**:
   - Not yet detailed with `/appkit.spec`
   - All sections have `[This section will be filled...]`

2. **Partially written**:
   - Some sections filled
   - Some sections still empty

3. **Fully written**:
   - Most sections filled
   - Can add/modify

### 4. Natural Language Analysis with User Value Focus

**Input Analysis**: "search and book available courts from main screen at once"

**고객 가치 분석**:
```
핵심 질문:
- 누가? → 퇴근길 직장인, 시간이 없는 사람
- 언제? → 이동 중, 짬날 때
- 왜? → 빠르게 주말 운동 계획 세우려고
- 어떻게? → 한 화면에서 모든 것 해결
- 가치? → 시간 절약 (15분 → 3초)

Map to sections:
- User Value: 3초 만에 예약 완료
- User Journey:
  - 앱 열기 → 날짜/시간 선택 → 예약 → 완료
  - 총 소요 시간: 3초
- Pain Points Solved:
  - 전화 대기 없음
  - 여러 코트 동시 확인
  - 즉시 확정

Business Rules (고객 관점):
  - 실시간 업데이트 (놓치지 않게)
  - 가격 투명 공개 (비교 가능)
  - 즉시 확정 알림 (안심)
```

**Input Analysis 2**: "time deal within 2 days of booking date, 30% discount"

**고객 가치 분석**:
```
핵심 질문:
- 누가? → 시간 유연한 프리랜서, 학생
- 언제? → 갑자기 시간 생겼을 때
- 왜? → 저렴하게 운동하고 싶어서
- 어떻게? → 자동으로 할인 적용
- 가치? → 30% 비용 절감

Map to sections:
- User Value: 정가의 70%로 운동
- User Scenario:
  - "내일 시간 비었네?" → 앱 확인 → "30% 할인!" → 즉시 예약
- Emotional Journey:
  - 발견 (😮) → 기쁨 (😊) → 만족 (😍)

Business Rules (고객 이익):
  - 자동 적용 (따로 쿠폰 입력 안 해도 됨)
  - 명확한 조건 표시 (언제 할인되는지 투명)
  - 다른 할인과 비교 (가장 이득인 것 자동 선택)
```

### 5. Spec Update (Incremental)

**Principles**:
1. **Preserve existing content**: Never delete
2. **Add new content**: Add natural language analysis results to relevant sections
3. **Prevent duplicates**: Don't add already existing content
4. **Maintain consistency**: Keep existing format and tone

**Update Example**:

**Before** (empty template):
```markdown
## User Journey & Screen Flow
[This section will be filled by /appkit.spec command]

## Business Rules
[This section will be filled by /appkit.spec command]
```

**After** (first `/appkit.spec` execution):
```markdown
## User Journey & Screen Flow

### 1. Main Screen
- **UI Elements**: Search bar (date, time), recommended court list
- **CTA**: "Search" button
- **Next**: Search results screen

### 2. Search Results Screen
- **UI Elements**: Filters (price, distance, rating), court cards (image, name, price, distance)
- **CTA**: Click court card
- **Next**: Court detail screen

### 3. Court Detail Screen
- **UI Elements**: Court info, reviews, available time slots
- **CTA**: "Book" button
- **Next**: Payment screen

## Business Rules
### Search Criteria
- Date: After today
- Time slot: Selectable
- Results: Show only available courts
```

**After** (second `/appkit.spec` execution - "sort by price and distance"):
```markdown
## User Journey & Screen Flow

### 1. Main Screen
- **UI Elements**: Search bar (date, time), recommended court list
- **CTA**: "Search" button
- **Next**: Search results screen

### 2. Search Results Screen
- **UI Elements**: Filters (price, distance, rating), sort options (price/distance), court cards  # Updated
- **CTA**: Click court card
- **Next**: Court detail screen

### 3. Court Detail Screen
- **UI Elements**: Court info, reviews, available time slots
- **CTA**: "Book" button
- **Next**: Payment screen

## Business Rules
### Search Criteria
- Date: After today
- Time slot: Selectable
- Results: Show only available courts

### Sort Options  # Added
- By price: Lowest first
- By distance: Closest first
- Default: By price
```

**After** (third `/appkit.spec` execution - "time deal 30% discount"):
```markdown
## Pricing & Promotion Logic
### Time Deal  # New section added
- Condition: Within 2 days of booking date
- Discount rate: 30%
- Application: Automatic
```

### 6. Auto-Completeness Check (고객 가치 중심)

After updating spec, automatically check customer value completeness:

**Check Sections**:
- ✅ User Value (고객이 얻는 가치)
- ✅ Target User (누가 쓸까?)
- ✅ User Scenario (언제/어떻게 쓸까?)
- ⏳ Pain Points Solved (해결되는 문제)
- ❌ Success Metrics (어떻게 성공 측정?)
- ⚠️ Edge Cases (예외 상황)

**Report to User**:
```markdown
✅ Spec 002-booking 고객 가치 업데이트!

💡 핵심 가치 분석:
- 누가: 30대 직장인 (퇴근길)
- 언제: 이동 중 짬날 때
- 왜: 주말 운동 예약
- 가치: 15분 → 3초 시간 절약

📝 업데이트된 내용:
- User Value: 3초 예약으로 시간 절약
- User Scenario: 퇴근길 지하철 예약 시나리오
- Pain Points: 전화 대기, 불확실성 해결

📋 완성도 체크:
- ✅ User Value (명확)
- ✅ Target User (구체적)
- ✅ User Scenario (생생함)
- ⏳ Pain Points (더 추가 가능)
  💡 제안: "주말 만석으로 운동 못함" 추가
- ❌ Success Metrics (미작성)
  💡 제안: "평균 예약 시간 3초 이하"
- ⚠️ Edge Cases (미흡)
  💡 제안: "동시 예약 충돌 처리"

💡 다음 단계:
더 많은 사용자 시나리오 추가:
  /appkit.spec 002-booking "프리랜서가 평일 낮 할인받기"
  /appkit.spec 002-booking "대학생 그룹 예약으로 절약"

📄 전체 spec 보기: docs/appkit/specs/002-booking/spec.md

📍 다음 단계: Step 4-5 - /appkit.customer (타겟 고객 정의 & 스토리텔링)
```

### 7. Completeness Check Criteria

**Section Status**:
- ✅ **Well-written**: Section has concrete content, no ambiguity
- ⏳ **Partially written**: Section exists but lacks details
- ⚠️ **Vague**: Section has content but vague or missing key parts
- ❌ **Not written yet**: Section is empty or only has placeholder

**Required Sections** (at minimum):
1. User Journey & Screen Flow (with screen details)
2. Business Rules
3. Dependencies

**Recommended Sections** (depending on spec type):
- Pricing & Promotion Logic (if pricing/discounts involved)
- Payment Flow (if payments involved)
- Cancellation & Refund (if cancellations possible)
- Edge Cases (always recommended)

## Section Mapping Guide (고객 가치 중심)

Natural language input → Customer value section mapping:

### User Value Related
**Keywords**: "절약", "빠른", "편리한", "쉬운", "자동", "한번에"
**Examples**:
- "3초 만에 예약" → User Value: 시간 절약
- "자동 할인 적용" → User Value: 비용 절감
- "원터치 결제" → User Value: 편의성

### Target User Related
**Keywords**: "직장인", "학생", "프리랜서", "주부", "시니어"
**Examples**:
- "바쁜 직장인을 위한" → Target User: 30-40대 직장인
- "학생 할인" → Target User: 대학생

### User Scenario Related
**Keywords**: "퇴근길", "점심시간", "주말", "갑자기", "급하게"
**Examples**:
- "퇴근길 지하철에서" → User Scenario: 이동 중 예약
- "주말 아침 급하게" → User Scenario: 당일 예약

### Payment Flow Related
**Keywords**: "payment", "fee", "payment method", "card", "cash", "bank transfer"
**Examples**:
- "online payment 5% fee" → Payment Flow
- "cash payment no fee" → Payment Flow

### Cancellation & Refund Related
**Keywords**: "cancel", "refund", "change", "modify"
**Examples**:
- "100% refund 24h before" → Cancellation & Refund
- "1 booking change allowed" → Cancellation & Refund

### Edge Cases Related
**Keywords**: "fail", "error", "concurrent", "duplicate", "timeout", "when empty", "exceed"
**Examples**:
- "first-come-first-served for concurrent bookings" → Edge Cases
- "rollback booking on payment failure" → Edge Cases

### Dependencies Related
**Keywords**: "need", "depend", "integrate", "reference"
**Inference**: When using data or functionality from other specs

## Important Notes

### 🔴 Mandatory Requirements

1. **Incremental update**:
   - Never delete existing content
   - Only add new content
   - Prevent duplicates

2. **Natural language analysis**:
   - Carefully analyze user input
   - Map to appropriate sections
   - If inference is ambiguous, add to most relevant section

3. **Maintain consistency**:
   - Keep existing format and tone
   - Consistent markdown style
   - Unified terminology

4. **Auto-completeness check**:
   - Check completeness after every update
   - Provide next step suggestions
   - Point out vague or missing parts

### 🟡 Analysis Guidelines

1. **Multiple section updates**:
   - Single natural language input can affect multiple sections
   - Update all relevant sections

2. **Inference and expansion**:
   - Don't just add explicit content
   - Include reasonable inferences
   - Example: "search" → search criteria, result display, empty result handling

3. **Cross-reference**:
   - Specify in Dependencies if related to other specs
   - Mention policy references if related to policies

### 🟢 Screen Flow Details

When updating User Journey & Screen Flow, include:

**For each screen**:
1. **Screen name**: Clear, descriptive name
2. **UI Elements**: Key visual elements users see
3. **CTA (Call-to-Action)**: Main buttons or actions
4. **Next**: Which screen comes next

**Example**:
```markdown
### 2. Search Results Screen
- **UI Elements**:
  - Filter bar (price range, distance, rating)
  - Sort dropdown (price/distance/rating)
  - Court cards with: thumbnail, name, price, distance, rating
  - "No results" message (when empty)
- **CTA**:
  - Click court card → Court detail
  - Adjust filters → Refresh results
- **Next**: Court detail screen or refined results
```

## Example Flow

```
# First execution
User: /appkit.spec 003-booking "search courts from main screen"
Claude: ✅ User Journey & Screen Flow, Business Rules updated
        📋 Payment Flow, Cancellation missing
        💡 Next: Add payment policy

# Second execution
User: /appkit.spec 003-booking "sort by price and distance"
Claude: ✅ User Journey, Business Rules updated (preserved + added)
        📋 Payment Flow, Cancellation still missing

# Third execution
User: /appkit.spec 003-booking "time deal 30% discount"
Claude: ✅ Pricing & Promotion Logic added (new section)
        📋 Payment Flow, Cancellation still missing

# Fourth execution
User: /appkit.spec 003-booking "online payment 5% fee"
Claude: ✅ Payment Flow added (new section)
        📋 Only Cancellation missing now
        💡 Almost complete! Just add cancellation policy
```
