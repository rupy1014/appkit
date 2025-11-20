---
description: 아이디어 스케치 - 막연한 아이디어를 서비스 컨셉으로 구체화
---

## Quick Reference
- **Workflow**: Step 1/7 (아이디어 스케치)
- **Token Budget**: ~3,000 tokens
- **Parallel Operations**: YES (file creation phase)
- **User Interaction**: REQUIRED (confirmation before file creation)
- **Progressive Loading**: NO (initial setup)

## User Input

```text
$ARGUMENTS
```

User input **must** be considered (if not empty).

## Overview

The text following `/appkit.new` is the app description. Assume `$ARGUMENTS` is always available in this conversation even if shown as-is. Don't ask again unless the user provides an empty command.

**This is Step 1 of the logical thinking 7-step workflow**:

```
논리적 사고 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?) ← YOU ARE HERE
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

Based on the app description, perform the following:

## Execution Flow

### 1. 아이디어 스케치 (고객 중심 대화)

**Input**: User's natural language app description (e.g., "Tennis court booking app with promotions and coupons")

**Step 1: 고객 문제 파악**
1. **무슨 문제를 해결하나?**:
   - 현재 고객이 겪는 불편함
   - 기존 솔루션의 한계
   - 해결되지 않은 니즈

2. **누가 이 문제를 겪나?**:
   - 주요 타겟 고객군
   - 그들의 특성과 행동 패턴
   - 문제의 심각도

**Step 2: 서비스 컨셉 제시**

Present customer-centric summary in this format:

```markdown
## 📋 서비스 컨셉

**서비스명**: [추론한 이름 또는 사용자 입력]

### 🎯 핵심 문제와 해결책

**고객이 겪는 문제**:
- "테니스 치고 싶은데 코트 예약이 너무 번거로워요"
- "전화로 일일이 확인해야 하고, 대기 시간도 길어요"
- "가격도 제각각이라 비교가 어려워요"

**우리의 해결책**:
- 3초 만에 실시간 예약
- 모든 코트 가격 한눈에 비교
- 자동 할인으로 30% 저렴하게

### 👥 타겟 고객

**Primary (핵심 고객)**:
- 30-40대 직장인
- 주말 운동을 원하지만 시간이 없는 사람
- 편의성과 시간 절약을 중시

**Secondary (보조 고객)**:
- 프리랜서 (시간 유연, 가격 민감)
- 대학생 (저렴한 가격 선호)

### 💎 핵심 가치 (왜 써야 하나?)

1. **시간 절약**: 15분 대기 → 3초 예약
2. **비용 절감**: 자동 할인으로 평균 30% 저렴
3. **확실한 예약**: 실시간 확인, 즉시 확정

### 🚀 차별점 (경쟁사와 뭐가 다른가?)

- 기존: 전화 예약, 불확실, 정가
- 우리: 앱 예약, 실시간, 자동 할인

### 📦 주요 기능 (고객 가치 중심)

1. **001-search**: 빠른 코트 검색
   - 위치 기반 자동 추천
   - 실시간 예약 가능 확인

2. **002-booking**: 간편 예약/결제
   - 3초 예약 완료
   - 원터치 결제

3. **003-discount**: 스마트 할인
   - 타임딜 자동 적용
   - 쿠폰 자동 추천

4. **004-manage**: 예약 관리
   - 예약 변경/취소
   - 알림 설정

5. **005-social**: 커뮤니티
   - 파트너 찾기
   - 리뷰/평점

### 💰 수익 모델

- 예약 수수료 (5-10%)
- 프리미엄 멤버십 (우선 예약권)
- 제휴 광고 (장비, 레슨)

---

이렇게 이해한 것이 맞나요? 수정하거나 추가하고 싶은 내용이 있나요?

특히:
- 핵심 고객이 맞나요?
- 해결하려는 문제가 정확한가요?
- 더 중요한 기능이 있나요?
```

**Step 3: Receive User Feedback**

Wait for user response:
- "Good", "Yes", "Proceed" → Move to Step 4
- Modification request → Update content and return to Step 2
- Additional features → Add to feature list and return to Step 2

**Example Dialog**:
```
User: "Lesson booking is important too. And we need instructor rating feature"

Claude:
Got it! I'll update as follows:

**Major Feature Specs (Updated)**:
1. 001-user: User authentication and profile management
2. 002-venue: Court information management
3. 003-lesson: Lesson information and instructor management (newly added)
4. 004-booking: Booking and payment system (courts + lessons)
5. 005-promotion: Coupons and promotions
6. 006-review: Facility and instructor reviews/ratings (instructor rating added)

Shall we proceed with this?
```

**Step 4: Final Confirmation**

When user confirms with "Good", "Proceed", etc.:

```
✅ App structure confirmed!

Creating files now...
```

### 2. Script Execution (After User Confirmation)

Execute only after user confirmation:

**Script**: `.app/scripts/init-app.sh --json --app-name "tymatch"`

**Script Actions**:
- Create `docs/appkit/` directory
- Create `docs/appkit/specs/` directory
- Create subdirectories for each confirmed spec (`001-user/`, `002-venue/`, ...)
- JSON output:
  ```json
  {
    "SPECS_DIR": "docs/appkit/specs",
    "APP_OVERVIEW": "docs/appkit/overview.md"
  }
  ```

**Important**:
- **No file creation before user confirmation**
- Script only handles directory creation and path output
- Natural language analysis and dialogue handled by Claude

### 3. Service Overview Document Creation

**File**: `docs/appkit/overview.md`

**Content**: Use **user-confirmed content** with customer focus

```markdown
# [Service Name] Service Concept

## 🎯 서비스 본질
[한 문장으로 서비스 정의]
예: "직장인의 주말 운동을 쉽게 만드는 테니스 코트 예약 서비스"

## 🔥 해결하는 문제
[User-confirmed problems]
- 번거로운 전화 예약 (15분 대기)
- 불투명한 가격 정보
- 원하는 시간대 확인 어려움

## 👥 타겟 고객
[User-confirmed target customers]

### Primary Persona
- 김대리 (35세, IT기업)
- Pain: "주말 운동하고 싶은데 예약이 너무 번거로워"
- Want: 빠른 예약, 확실한 시간 확보

### Secondary Personas
- 프리랜서: 평일 낮 저렴한 시간대 활용
- 대학생: 그룹 예약으로 할인 받기

## 💎 핵심 가치 제안
[User-confirmed value propositions]
1. **시간 절약**: 15분 → 3초
2. **비용 절감**: 자동 할인 30%
3. **확실성**: 실시간 확인 & 즉시 확정

## 📦 주요 기능 (고객 가치 중심)
[User-confirmed features with customer value]
- **001-search**: 3초 만에 찾는 완벽한 코트
- **002-booking**: 클릭 한 번으로 예약 완료
- **003-discount**: 자동으로 적용되는 최저가
- **004-manage**: 언제든 변경 가능한 유연함
- **005-social**: 함께 운동할 파트너 찾기

## 🚀 MVP 로드맵
Phase 0 (2주): 핵심 예약 기능
Phase 1 (1개월): 할인 & 리뷰
Phase 2 (3개월): 커뮤니티 & 확장

## 💰 비즈니스 모델
[User-confirmed business model]
- 예약 수수료 (5-10%)
- 프리미엄 멤버십
- 제휴 마케팅

## 📊 성공 지표
- Week 1: 10명 사용자 확보
- Week 2: 10건 예약 달성
- Month 1: NPS 30+ 달성
```

**Important**: Use content presented in Step 2 and confirmed by user **as-is**

### 4. Individual Spec Draft Creation (Based on Overview.md)

**⚡ CRITICAL - PARALLEL EXECUTION REQUIRED**:
Create ALL spec files in a SINGLE message with multiple Write tool calls. Do NOT create files sequentially.

**Performance Impact**:
- ❌ Sequential: 10 files × 3 seconds = 30 seconds
- ✅ Parallel: 1 message with 10 Write calls = 3 seconds
- **10x speed improvement**

Create **initial draft** `spec.md` file in each spec directory based on overview.md content:

**Important**: This creates **first draft**, not empty templates. Extract relevant information from overview.md for each feature.

**Approach**:
1. Read the feature description from overview.md (주요 기능 section)
2. Extract customer value, target user, and workflow hints
3. Create initial draft with inferred content
4. Mark sections that need `/appkit.spec` for further detailing

**Execution Pattern**:
Execute ALL file creations in ONE message (example pattern shown below - do not copy verbatim):
- Use multiple Write tool calls in a single message
- Each Write call creates one spec file
- All spec files created in parallel (5-10 files typical)

**File**: `docs/appkit/specs/001-[feature-name]/spec.md`

**Content**: Draft with overview-based initial content

```markdown
# Spec: 001-persona

## Feature Name
페르소나 생성 및 관리

## User Value (고객 가치)
[Extract from overview.md's feature description]
- 100가지 다양한 스타일로 브랜드 노출 확대
- 카테고리별 최적화된 인플루언서 확보

## Target User (누가 쓸까?)
[Infer from overview.md's 타겟 고객 section]
- Primary: 서비스 관리자
- Use case: 초기 셋업 시 다양한 페르소나 생성

## User Journey & Screen Flow
[Extract workflow from overview.md's 핵심 워크플로우]

### 1. 페르소나 생성 화면
- **UI Elements**: 카테고리 선택, 개수 설정, 생성 버튼
- **CTA**: "100명 자동 생성" 버튼
- **Next**: 페르소나 목록 화면

### 2. 페르소나 목록 화면
- **UI Elements**: 페르소나 카드 그리드 (이름, 카테고리, 상태)
- **CTA**: 미드저니 프롬프트 export, 프로필 이미지 업로드
- **Next**: 개별 페르소나 상세

## Business Rules
[Extract from overview.md's feature description]
- 카테고리별 페르소나 자동 생성 (Beauty 25명, Fashion 25명, etc.)
- 미드저니용 프롬프트 export 기능
- 프로필 이미지 업로드 시스템

## Edge Cases
[Initial inference - needs /appkit.spec for details]
- 페르소나 생성 실패 시 재시도 로직
- 중복 페르소나 체크

## Dependencies
[Infer from overview.md workflow]
- None (initial setup feature)

---

💡 **더 구체화하려면**:
```
/appkit.spec 001-persona "카테고리별 비율 조정 기능"
/appkit.spec 001-persona "페르소나별 톤앤매너 설정"
```
```

**Content Generation Strategy**:

For each spec (001-010), extract from overview.md:

1. **Feature Name**: Use Korean name from 주요 기능 section
2. **User Value**: Extract from 핵심 가치 제안 or feature description
3. **Target User**: Infer from 타겟 고객 (관리자 vs 광고주)
4. **User Journey**: Extract from 핵심 워크플로우 section
5. **Business Rules**: Extract explicit rules from feature description
6. **Edge Cases**: Basic inference (mark as "needs detailing")
7. **Dependencies**: Infer from workflow order

**Example Mapping** (from AI Influencer Network overview.md):

```
001-persona →
  - Extract: "100명의 다양한 인플루언서 생성"
  - User Value: 카테고리별 최적화된 인플루언서 풀 확보
  - Journey: 카테고리 선택 → 자동 생성 → 미드저니 export

003-content-composer →
  - Extract: "크롤링 요소 조합으로 빠른 제작"
  - User Value: 검증된 요소 조합으로 시행착오 최소화
  - Journey: 크롤링 갤러리 → 요소 선택 → 나노바나나 생성

006-brand-site →
  - Extract: "광고주가 쉽게 의뢰"
  - User Value: 빠른 캠페인 실행, 다양한 타겟층 공략
  - Journey: 브랜드 등록 → 카테고리 선택 → 캐릭터 추천
```

**Files to Create** (with overview-based drafts):
- `docs/appkit/specs/001-persona/spec.md`
- `docs/appkit/specs/002-reference-crawl/spec.md`
- `docs/appkit/specs/003-content-composer/spec.md`
- `docs/appkit/specs/004-caption-generator/spec.md`
- `docs/appkit/specs/005-approval/spec.md`
- `docs/appkit/specs/006-brand-site/spec.md`
- `docs/appkit/specs/007-ad-content/spec.md`
- `docs/appkit/specs/008-posting/spec.md`
- `docs/appkit/specs/009-engagement/spec.md`
- `docs/appkit/specs/010-analytics/spec.md`

### 5. Completion Report

Report to user:

```
✅ 서비스 컨셉 정의 & 기능 초안 생성 완료!

📁 생성된 파일:
- docs/appkit/overview.md (서비스 컨셉)
- docs/appkit/specs/001-search/spec.md (검색 - 초안 생성됨 ✨)
- docs/appkit/specs/002-booking/spec.md (예약 - 초안 생성됨 ✨)
- docs/appkit/specs/003-discount/spec.md (할인 - 초안 생성됨 ✨)
- docs/appkit/specs/004-manage/spec.md (관리 - 초안 생성됨 ✨)
- docs/appkit/specs/005-social/spec.md (커뮤니티 - 초안 생성됨 ✨)

✨ 변경사항: 빈 템플릿이 아닌 overview.md 기반 **초안**이 생성되었습니다!
각 spec에는 이미 다음 내용이 포함되어 있습니다:
- User Value (고객 가치)
- Target User (타겟 고객)
- User Journey (기본 화면 흐름)
- Business Rules (핵심 규칙)
- Dependencies (의존성)

🎯 핵심 가치:
- 시간 절약: 15분 → 3초
- 비용 절감: 30% 자동 할인
- 확실한 예약: 실시간 확정

👥 타겟 고객:
- Primary: 30-40대 직장인
- Secondary: 프리랜서, 대학생

📝 다음 단계 (논리적 사고 흐름):

**Step 2 - 기능 구체화 (/appkit.spec)**
이미 초안이 있으니, 더 구체적인 시나리오를 추가하세요:
  /appkit.spec 001-search "위치 기반으로 가까운 코트 찾기, 거리순 정렬"
  /appkit.spec 002-booking "퇴근길 지하철에서 3초 예약, 원터치 결제"
  /appkit.spec 003-discount "타임딜 자동 적용, 중복 쿠폰 불가"

**Step 3 - 고객 스토리 (/appkit.customer)**
타겟 페르소나의 하루와 문제 해결 스토리:
  /appkit.customer

**Step 4 - 세일즈 랜딩 (/appkit.sales)**
광고주를 설득하는 랜딩 페이지:
  /appkit.sales

📍 현재 위치: Step 1/7 완료 (아이디어 스케치 + 초안 생성)
📍 다음 단계: Step 2 - /appkit.spec (기능 구체화)

💡 Tip: 각 spec 파일을 열어보세요. 이미 기본 구조가 채워져 있어서
      `/appkit.spec`으로 추가 디테일만 넣으면 됩니다!
```

## Important Notes

### 🔴 Mandatory Requirements

1. **Interactive process required**:
   - **Never create files immediately**
   - Always present summary in Step 2
   - Create files only after user confirmation

2. **Handle user feedback**:
   - "Good", "Yes", "Proceed" → Proceed with file creation
   - Modification request → Update and re-present
   - Additional features → Update list and re-present
   - If uncertain, ask additional questions

3. **Iterate before confirmation**:
   - Repeat Steps 2-3 until user is satisfied
   - Don't rush, have thorough dialogue

### 🟡 Analysis Guidelines

1. **Natural language analysis**:
   - Carefully analyze user input
   - Infer domain and business model
   - Derive reasonable major features (5-8)
   - Fill gaps with questions

2. **Numbering system**:
   - Use 3-digit numbers (001, 002, 003, ...)
   - Sort in logical order (auth → core features → supplementary features)

3. **Feature names**:
   - Short and clear (user, venue, booking, promotion)
   - Use lowercase English with hyphens

### 🟢 Technical Details

1. **Script execution**:
   - Execute only after user confirmation
   - If script doesn't exist, create directories manually
   - Parse JSON output to confirm paths

2. **Incremental detailing**:
   - This stage creates **structure only**
   - Details added with `/appkit.spec` command

## Example Flow

```
User: /appkit.new Tennis court booking app

Claude: [Presents Step 2 summary]

User: Add lesson booking too

Claude: [Presents updated summary]

User: Good!

Claude: ✅ Confirmed! Creating files...
[Executes file creation]
```
