# AppKit Framework

**아이디어를 고객 가치로 변환하는 논리적 사고 프레임워크**

---

## 🎯 Overview

AppKit은 막연한 아이디어를 고객 중심으로 구체화하여 MVP부터 세일즈까지 설계하는 프레임워크입니다.

**핵심 철학**:
1. 고객 가치 우선 → 기능이 아닌 고객의 문제 해결 중심
2. 논리적 사고 연습 → 큰 작업을 작은 단계로 쪼개기
3. 스토리텔링 기반 → 고객의 하루와 고민을 이해하고 설득
4. MVP 중심 실행 → 최소한의 범위로 최대한의 검증

---

## 📋 Complete Workflow (논리적 사고 7단계)

```
아이디어 구체화 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

---

## 🔧 Commands

### 1. `/appkit.new` - 아이디어 스케치

**Purpose**: 막연한 아이디어를 서비스 컨셉으로 구체화

**Input**:
```
/appkit.new Tennis court booking app with coupons and promotions
```

**Output**:
- `docs/appkit/overview.md` - 서비스 컨셉 & 핵심 가치
- `docs/appkit/specs/001-user/spec.md` - 빈 템플릿
- `docs/appkit/specs/002-venue/spec.md` - 빈 템플릿
- `docs/appkit/specs/003-booking/spec.md` - 빈 템플릿
- ...

**Key Features**:
- 서비스 본질 파악 (무슨 문제를 해결하나?)
- 예상 고객군 추론 (누가 쓸까?)
- 핵심 가치 제안 (왜 써야 할까?)
- 경쟁 차별점 식별 (다른 서비스와 뭐가 다른가?)

---

### 2. `/appkit.spec` - 기능 구체화

**Purpose**: 필요한 기능을 도출하고 사용자 관점에서 구체화

**Input**:
```
/appkit.spec 003-booking "search courts from main screen"
/appkit.spec 003-booking "time deal 30% discount within 2 days"
/appkit.spec 003-booking "cancel 24h+ before for 100% refund"
```

**Output**:
- `docs/appkit/specs/003-booking/spec.md` 업데이트 (증분식 누적)

**Key Questions for Each Feature**:
- **뭐가 필요할까?** → 필요한 기능들 도출
- **누가 쓸까?** → 타겟 사용자 프로파일
- **언제 쓸까?** → 사용 시나리오와 상황
- **왜 쓸까?** → 해결하려는 문제나 욕구
- **어떻게 쓸까?** → 구체적인 사용 플로우
- **가치는?** → 사용자가 얻는 이익

**중요**: 기술 구현보다 사용자 가치에 집중!

---

### 3. `/appkit.customer` - 고객 스토리

**Purpose**: 타겟 고객을 명확히 하고 그들의 하루와 고민을 스토리로 구성

**Input**:
```
/appkit.customer
/appkit.customer "30대 직장인 주말 운동"
```

**Output**:
- `docs/appkit/customer-persona.md` - 고객 페르소나
- `docs/appkit/customer-journey.md` - 고객 여정 지도

**What it does**:
1. **페르소나 구성**:
   - Demographics: 나이, 직업, 소득, 거주지
   - Psychographics: 라이프스타일, 가치관, 관심사
   - Pain Points: 현재 겪는 문제와 불편함
   - Goals: 달성하고 싶은 목표

2. **고객의 하루 스토리텔링**:
   ```
   07:00 - 출근 준비하며 "오늘도 운동 못하겠네..."
   09:00 - 회사 도착 "주말엔 꼭 테니스 쳐야지"
   12:00 - 점심시간 "코트 예약하려니 전화해야 하네..."
   18:00 - 퇴근 "주말 코트 풀부킹이라니..."
   21:00 - 집 도착 "내일 아침 일찍 전화해야겠다"
   ```

3. **문제 해결 시나리오**:
   - Before: 복잡한 예약 과정, 불확실한 가능 시간
   - After: 앱으로 간편 예약, 실시간 확인, 할인까지

**중요**: 고객 중심 사고의 핵심 - 기능이 아닌 고객의 삶을 이해!

---

### 4. `/appkit.sales` - 세일즈 랜딩 구성

**Purpose**: 고객을 설득하는 세일즈 메시지 구성

**Input**:
```
/appkit.sales
/appkit.sales "time-saving for busy professionals"
```

**Output**:
- `docs/appkit/sales-landing.md` - 세일즈 랜딩 구조
- `docs/appkit/value-proposition.md` - 가치 제안

**Landing Structure**:
1. **Hook (문제 공감)**:
   - "매번 전화로 테니스 코트 예약하느라 지치셨나요?"

2. **Problem Agitation (문제 심화)**:
   - 전화 대기 시간 평균 15분
   - 원하는 시간대 이미 만석
   - 가격 비교 불가능

3. **Solution (해결책 제시)**:
   - 3초 만에 실시간 예약
   - 모든 코트 가격 한눈에 비교
   - 자동 할인 적용

4. **Social Proof (사회적 증명)**:
   - "이미 5,000명의 테니스 동호인이 사용 중"
   - 사용자 후기와 평점

5. **CTA (행동 유도)**:
   - 첫 예약 30% 할인
   - 지금 가입하고 혜택받기

**중요**: 기능 나열이 아닌, 고객 문제 해결 스토리!

---

### 5. `/appkit.mvp` - MVP 범위 정의

**Purpose**: 최소한의 기능으로 최대한의 검증

**Input**:
```
/appkit.mvp
/appkit.mvp "2-week validation"
```

**Output**:
- `docs/appkit/mvp-scope.md` - MVP 범위 정의
- `docs/appkit/mvp-metrics.md` - 검증 지표

**MVP Scoping Process**:
1. **핵심 가치 파악**:
   - 고객이 가장 원하는 ONE thing은?
   - 없으면 서비스 의미가 없는 기능은?

2. **Phase 분류**:
   ```
   Phase 0 (MVP - 2주):
   - 코트 검색/예약 (핵심)
   - 간단한 결제

   Phase 1 (MVP+ - 1개월):
   - 사용자 리뷰
   - 할인 쿠폰

   Phase 2 (확장 - 3개월):
   - 커뮤니티 기능
   - 코칭 매칭
   ```

3. **검증 지표 설정**:
   - Success Metrics: 주간 예약 10건
   - Learning Metrics: 이탈 구간, 불만 사항
   - Next Decision: Phase 1 진행 여부

**MVP 원칙**:
- ❌ "있으면 좋을" 기능 제외
- ✅ "없으면 안되는" 기능만 포함
- 목표: 빠른 시장 검증, not 완벽한 제품

---


## 🌊 Workflow Example (고객 중심 논리적 사고)

### Example: Tennis Court Booking App

```bash
# Step 1: 아이디어 스케치 - "어떤 서비스인지?"
$ /appkit.new Tennis court booking with coupons and time deals

Claude:
📋 서비스 컨셉:
- 문제: 테니스 코트 예약이 번거롭고 비싸다
- 해결: 모바일로 간편 예약 + 자동 할인
- 타겟: 주말 운동을 원하는 30-40대 직장인
- 가치: 시간 절약, 비용 절감

주요 기능 분류:
- 001-user: 사용자 인증
- 002-venue: 코트 관리
- 003-booking: 예약/결제
- 004-promotion: 할인/쿠폰
- 005-review: 리뷰

✅ Created service concept & 5 feature specs

# Step 2: 기능 구체화 - "뭐가 필요할까? 누가 쓸까?"
$ /appkit.spec 003-booking "search courts from main screen"

💡 사용자 가치 분석:
- 뭐가 필요? → 실시간 코트 검색 기능
- 누가? → 퇴근 후 피곤한 직장인
- 언제? → 지하철/버스에서 이동 중
- 왜? → 빠르게 주말 운동 계획 세우기
- 어떻게? → 원터치로 가까운 코트 찾기
- 가치? → 5초 만에 예약 가능 확인

✅ User value added to spec

$ /appkit.spec 003-booking "time deal 30% within 2 days"

💡 사용자 가치 분석:
- 뭐가 필요? → 시간 기반 자동 할인 시스템
- 누가? → 유연한 시간대 가능한 프리랜서
- 언제? → 갑자기 시간이 생겼을 때
- 왜? → 저렴하게 운동하고 싶어서
- 가치? → 정가의 70%로 즉시 예약

✅ Features defined with user value

# Step 3: 고객 스토리 - "고객의 하루, 고민, 해결"
$ /appkit.customer

🎯 Primary Persona: 김대리 (35세, IT 기업)

하루 스토리:
07:00 - "오늘도 운동 못하겠네..." (죄책감)
12:00 - "주말엔 테니스 쳐야지" (결심)
18:00 - "코트 예약 전화... 귀찮다" (좌절)
19:00 - [앱 발견] "3초 만에 예약?" (희망)
19:02 - "토요일 오전 예약 완료!" (만족)
토요일 - "운동 후 상쾌한 주말" (성취)

✅ Customer persona & journey mapped

# Step 4: 세일즈 랜딩 구성 - "어떻게 설득할까?"
$ /appkit.sales

📢 Landing Message:

[Hook]
"매주 테니스 치고 싶은데, 예약이 너무 번거로우신가요?"

[Problem]
- 전화 대기 15분
- 원하는 시간 항상 만석
- 비싼 정가

[Solution]
"3초 예약, 자동 할인, 실시간 공석 확인"

[Proof]
"이미 5,000명이 매주 사용 중"

[CTA]
"지금 가입하고 첫 예약 30% 할인받기"

✅ Sales landing created

# Step 5: MVP 범위 - "최소한으로 검증하려면?"
$ /appkit.mvp

🎯 MVP Scope (2주 검증):

Phase 0 (핵심만):
- 코트 검색/예약
- 간단 결제
목표: 주 10건 예약

Phase 1 (1개월):
- 할인 쿠폰
- 사용자 리뷰
목표: 재방문율 30%

Phase 2 (3개월):
- 커뮤니티
- 코칭 매칭

✅ MVP phases defined

# Step 6: 기획 정돈 - "기획이 일관적인가?"
$ /appkit.merge

🔄 Planning Consolidation:

용어 통일성 확인:
- "예약" vs "부킹" → "예약"으로 통일
- "사용자" vs "유저" → "사용자"로 통일

기능 중복 제거:
- spec 3개소에서 발견된 "실시간 알림" → 하나로 통합
- customer journey와 sales의 메시지 일관성 확보

고객 여정 - 기능 매핑:
✅ "주말 운동 계획" → 검색 기능
✅ "간편한 예약" → 원터치 예약
✅ "비용 절감" → 자동 할인

✅ Planning consolidated

# Step 7: 개발 준비 - "어떻게 만들까?"
$ /appkit.design

🏗️ Technical Design:

ERD 설계:
- User, Venue, Booking, Payment 엔티티
- 관계 정의 및 제약조건

API 엔드포인트:
- POST /bookings (예약 생성)
- GET /venues?location=... (코트 검색)
- POST /payments (결제 처리)

기술 정책:
- Rate Limiting: 시간당 100회
- Error Handling: 재시도 3회
- Content Safety: 필터 규칙

✅ 아이디어 구체화 완료!
이제 개발을 시작할 수 있습니다.
```

---

### 6. `/appkit.merge` - 기획 정돈

**Purpose**: 흩어진 기획 문서들을 통합하고 일관성 확보

**Input**:
```
/appkit.merge
/appkit.merge "용어 통일 중점"
```

**Output**:
- `docs/appkit/merge/concept-map.md` - 통합 컨셉 맵
- `docs/appkit/merge/journey-feature-map.md` - 고객 여정 - 기능 매핑
- `docs/appkit/merge/terminology.md` - 표준 용어 사전
- `docs/appkit/merge/consolidated-specs.md` - 통합된 기능 명세

**What it does**:
1. **용어 통일성 확인**:
   - spec, customer, mvp의 용어 비교
   - 표준 용어 사전 생성

2. **기능 중복 제거**:
   - 여러 문서에 흩어진 동일 기능 통합
   - 기획 레벨에서 중복 해소

3. **고객 가치 일관성**:
   - customer journey와 sales 메시지 일관성
   - 핵심 가치 제안 명확화

**중요**: MVP 범위 정의 후, 개발 준비 전에 실행!

---

### 7. `/appkit.design` - 개발 준비

**Purpose**: 개발에 필요한 기술 스펙 생성 (ERD, API, 정책)

**Input**:
```
/appkit.design
/appkit.design "RESTful API 중점"
```

**Output**:
- `docs/appkit/design/entities.md` - ERD 및 데이터 모델
- `docs/appkit/design/apis.md` - API 엔드포인트 설계
- `docs/appkit/design/tech-policies.md` - 기술 정책
- `docs/appkit/design/screen-api-map.md` - 화면-API 매핑

**What it does**:
1. **ERD 설계**:
   - 엔티티 및 관계 정의
   - Mermaid 다이어그램 생성

2. **API 엔드포인트 설계**:
   - RESTful API 명세
   - Request/Response 예시

3. **기술 정책 정의**:
   - Rate Limiting
   - Error Handling
   - Content Safety
   - Data Management

**중요**: merge 완료 후 개발 직전에 실행!

---


---

## 🎓 논리적 사고 7단계와 명령어

| 단계 | 질문 | 명령어 |
|------|------|--------|
| 1. 아이디어 스케치 | 어떤 서비스인가? | `/appkit.new` |
| 2. 기능 구체화 | 뭐가 필요할까? 누가/어떻게 쓸까? | `/appkit.spec` |
| 3. 고객 스토리 | 고객의 하루, 고민, 해결은? | `/appkit.customer` |
| 4. 세일즈 구성 | 어떻게 설득할까? | `/appkit.sales` |
| 5. MVP 범위 | 최소한으로 검증하려면? | `/appkit.mvp` |
| 6. 기획 정돈 | 기획이 일관적인가? | `/appkit.merge` |
| 7. 개발 준비 | 어떻게 만들까? | `/appkit.design` |

---

## 💡 Best Practices (논리적 사고 연습)

### 1. 고객부터 시작하기
- 기능이 아닌 고객의 문제부터 생각하세요
- "누가 쓸까?" 질문을 계속하세요

### 2. 작은 단계로 쪼개기
- 큰 작업을 7-10개 작은 단계로 나누세요
- 각 단계가 명확한 결과물을 갖도록 하세요

### 3. 스토리텔링으로 검증
- 고객의 하루를 그려보세요
- Before/After 시나리오를 구성하세요

### 4. MVP 먼저, 완벽은 나중에
- "없으면 안되는" 기능만 Phase 0에
- "있으면 좋은" 기능은 Phase 1+로

### 5. 세일즈 관점 유지
- 기능 설명이 아닌 가치 설명
- 고객이 얻는 이익 중심으로

### 6. 빠른 검증, 빠른 피벗
- 2주 안에 MVP 검증
- 실패해도 빠르게 방향 전환

### 7. 측정 가능한 목표
- 모든 Phase에 구체적 지표 설정
- 정성적 + 정량적 지표 균형

---

## 📂 Generated File Structure

```
docs/appkit/
├── overview.md                    # 1. 서비스 컨셉 (/appkit.new)
├── specs/
│   ├── 001-search/
│   │   └── spec.md               # 2. 기능 구체화 (/appkit.spec)
│   ├── 002-booking/
│   │   └── spec.md
│   └── ...
├── customer-persona.md            # 3. 타겟 고객 (/appkit.customer)
├── customer-journey.md            # 3. 고객 스토리 (/appkit.customer)
├── sales-landing.md               # 4. 세일즈 메시지 (/appkit.sales)
├── value-proposition.md           # 4. 가치 제안 (/appkit.sales)
├── mvp-scope.md                   # 5. MVP 범위 (/appkit.mvp)
├── mvp-metrics.md                 # 5. 검증 지표 (/appkit.mvp)
├── merge/                         # 6. 기획 정돈 (/appkit.merge)
│   ├── concept-map.md             # 통합 컨셉 맵
│   ├── journey-feature-map.md     # 고객 여정 - 기능 매핑
│   ├── terminology.md             # 표준 용어 사전
│   └── consolidated-specs.md      # 통합된 기능 명세
└── design/                        # 7. 개발 준비 (/appkit.design)
    ├── entities.md                # ERD 및 데이터 모델
    ├── apis.md                    # API 엔드포인트 설계
    ├── tech-policies.md           # 기술 정책
    └── screen-api-map.md          # 화면-API 매핑
```

---

## 🚀 Quick Start

```bash
# 1. 아이디어 스케치
/appkit.new "당근마켓처럼 중고거래 앱"

# 2. 기능 구체화
/appkit.spec 001-search "위치 기반 상품 검색"
/appkit.spec 002-chat "구매자와 판매자 채팅"

# 3. 고객 스토리
/appkit.customer "20-30대 중고거래 선호"

# 4. 세일즈 메시지 구성
/appkit.sales "편리함과 신뢰 강조"

# 5. MVP 범위 정의
/appkit.mvp "2주 내 출시 목표"

# 6. 기획 정돈
/appkit.merge

# 7. 개발 준비
/appkit.design
```

---


## 📖 Philosophy (논리적 사고 철학)

> "아이디어는 고객의 문제에서 시작되고, 논리적 단계로 구체화된다."

AppKit은 다음을 믿습니다:

1. **고객 문제 우선**: 기능보다 고객의 Pain Point 해결
2. **논리적 분해**: 큰 작업을 작은 단계로 쪼개기
3. **스토리텔링**: 고객의 하루를 이해하고 공감
4. **빠른 검증**: MVP로 시장 반응 먼저 확인
5. **가치 중심**: 기술이 아닌 고객 가치로 설득
6. **측정과 학습**: 모든 단계에서 배우고 개선

---

**Built with ❤️ for Product Managers, Designers, and Developers**

**Version**: 5.0.0 (7-Step Logical Thinking)
**Last Updated**: 2025-11-20
**Key Update**: 논리적 사고 7단계로 재구성, merge(기획 정돈)와 design(개발 준비) 분리
