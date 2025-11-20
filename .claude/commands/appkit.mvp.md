# appkit.mvp

**최소한의 기능으로 최대한의 검증을 하는 MVP 범위 정의 명령어**

---

## Overview

**This is Step 5 of the logical thinking 7-step workflow**:

```
논리적 사고 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?) ← YOU ARE HERE
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

## Purpose

핵심 가치만 구현하여 빠르게 시장 검증을 하기 위한 MVP 범위를 정의합니다.
"있으면 좋은" 기능을 제외하고 "없으면 안되는" 기능만 선별합니다.

**핵심 질문**: "최소한으로 검증하려면 뭐가 필요할까?"

---

## When to Use

- `/appkit.sales`로 가치 제안을 정의한 후 (Step 4 완료 후)
- 개발 시작 전 범위를 정해야 할 때
- 리소스가 제한적일 때
- 빠른 시장 검증이 필요할 때

---

## Usage

```bash
/appkit.mvp
/appkit.mvp "2-week validation"
/appkit.mvp "budget: 500만원"
/appkit.mvp "target: early adopters only"
```

---

## What I'll Do

### 1. MVP 정의 프레임워크

```markdown
## MVP Definition Framework

### The ONE Thing Test
"만약 딱 하나의 기능만 만들 수 있다면?"
→ 그것이 진짜 핵심 가치

### Concierge MVP vs Product MVP
- Concierge: 수동으로 서비스 제공 (검증용)
- Product: 자동화된 제품 (확장용)

### MLP (Minimum Lovable Product)
- Minimum: 최소 기능
- Viable: 사용 가능
- Lovable: 사랑받을 만한
→ MVP도 완성도는 있어야 함
```

### 2. Phase별 기능 분류

```markdown
## MVP Phases

### Phase 0: Core MVP (2주)
"없으면 서비스가 성립 안 되는 기능"

#### Must Have (핵심)
✅ 코트 검색/조회
✅ 실시간 예약
✅ 간단 결제
✅ 예약 확인

#### 구현 수준
- UI: 기본 모바일 웹 (앱 개발 X)
- 백엔드: 최소 API (5-7개)
- 결제: 간편결제 1종 (카드)
- 인증: 소셜 로그인 1종 (카카오)

#### 제외할 것
❌ 회원 등급 시스템
❌ 리뷰/평점
❌ 쿠폰/포인트
❌ 푸시 알림
❌ 커뮤니티

#### 검증 목표
- 주간 예약 10건 달성
- 사용자 10명 확보
- 핵심 플로우 검증


### Phase 1: Enhanced MVP (1개월)
"사용자 만족도를 높이는 기능"

#### Should Have (개선)
✅ 할인/쿠폰 시스템
✅ 사용자 리뷰
✅ 예약 변경/취소
✅ 다중 결제 수단

#### 검증 목표
- 재방문율 30%
- 주간 예약 50건
- NPS 40 이상


### Phase 2: Growth (3개월)
"성장과 확장을 위한 기능"

#### Nice to Have (확장)
✅ 커뮤니티 기능
✅ 코칭 매칭
✅ 토너먼트 개최
✅ 장비 대여

#### 검증 목표
- MAU 1,000명
- 월 매출 1,000만원
- 바이럴 계수 1.2
```

### 3. MVP 검증 지표 설정

```markdown
## MVP Metrics

### 1️⃣ Success Metrics (성공 지표)
"목표 달성 여부"

#### Quantitative (정량)
- 주간 활성 사용자 (WAU): 10명
- 주간 예약 건수: 10건
- 전환율: 방문자의 10% 예약
- 결제 성공률: 90%

#### Qualitative (정성)
- "편리하다" 피드백 70%
- "다시 쓸 것" 응답 80%
- 추천 의향 (NPS): 30+


### 2️⃣ Learning Metrics (학습 지표)
"무엇을 배울 것인가"

#### User Behavior
- 이탈 구간: 어디서 포기하나?
- 사용 시간대: 언제 가장 활발한가?
- 검색 패턴: 뭘 찾고 있나?
- 실패 케이스: 왜 예약 안 하나?

#### Product-Market Fit Signals
- Organic Growth: 자연 유입 있나?
- Retention: 다시 오나?
- Referral: 추천하나?
- Payment: 돈을 내나?


### 3️⃣ Pivot Indicators (피벗 신호)
"방향 전환이 필요한 시점"

🚨 Danger Signals
- 2주 후 WAU < 5명
- 전환율 < 3%
- NPS < 0
- 일일 사용 시간 < 1분

→ Action: 가치 제안 재검토
```

### 4. MVP 개발 우선순위 매트릭스

```markdown
## Priority Matrix

        High Impact ↑

    [P0: 코트 예약]  |  [P1: 할인 시스템]
    Must Do Now       |  Do Next
    __________________|__________________
                      |
    [P3: 푸시 알림]   |  [P2: 리뷰 시스템]
    Don't Do          |  Do Later
                      |
                      → High Effort

### Priority Scoring
Impact (영향도) x Confidence (확신도) / Effort (노력)

예시:
- 코트 예약: 10 x 10 / 3 = 33.3 (P0)
- 커뮤니티: 5 x 3 / 8 = 1.9 (P3)
```

### 5. MVP 실행 로드맵

```markdown
## Execution Roadmap

### Week 1-2: Build Phase 0
Day 1-3: 기본 UI/UX
- 검색 화면
- 예약 화면
- 확인 화면

Day 4-7: 핵심 백엔드
- 예약 API
- 결제 연동
- 알림 발송

Day 8-10: 통합 테스트
- End-to-end 테스트
- 결제 테스트
- 부하 테스트

Day 11-14: Soft Launch
- 베타 사용자 10명
- 피드백 수집
- 긴급 수정


### Week 3-4: Validate & Iterate
- 지표 측정
- 사용자 인터뷰
- 개선사항 반영
- Phase 1 결정


### Week 5-8: Build Phase 1
(If Phase 0 validated)
- 할인 시스템
- 리뷰 기능
- UX 개선
```

### 6. MVP 체크리스트

```markdown
## MVP Checklist

### Before Launch
□ 핵심 가치 명확한가?
□ 타겟 사용자 명확한가?
□ 성공 지표 정의했나?
□ 실패 기준 정의했나?
□ 2주 안에 가능한가?

### During Development
□ Scope creep 발생하지 않았나?
□ "하나 더" 유혹 거부했나?
□ 핵심 플로우만 집중했나?

### After Launch
□ 정량 지표 달성했나?
□ 정성 피드백 긍정적인가?
□ 다음 단계 명확한가?
```

---

## Output Files

### 생성될 파일들:

1. **`docs/appkit/mvp-scope.md`**
   - Phase별 기능 목록
   - 포함/제외 기능
   - 우선순위 매트릭스

2. **`docs/appkit/mvp-metrics.md`**
   - 성공 지표
   - 학습 지표
   - 피벗 기준

---

## Integration Points

### 다른 명령어와의 연계:

- **From `/appkit.customer`**: Primary 페르소나의 핵심 문제
- **From `/appkit.sales`**: 검증할 핵심 가치
- **To `/appkit.merge`**: MVP Phase 0 기능의 구현 준비

---

## Examples

### Example 1: 2주 검증 MVP
```bash
$ /appkit.mvp "2-week validation"

🎯 MVP Scope Defined

Phase 0 (2 weeks):
✅ Search (location-based)
✅ Booking (real-time)
✅ Payment (simple)
✅ Confirmation (email)

Excluded:
❌ Reviews (Phase 1)
❌ Discounts (Phase 1)
❌ Community (Phase 2)

Success Criteria:
- 10 bookings/week
- 10 active users
- NPS > 30

✅ Generated mvp-scope.md
✅ Generated mvp-metrics.md
```

### Example 2: 예산 제약 MVP
```bash
$ /appkit.mvp "budget: 500만원"

💰 Budget-Constrained MVP

Concierge MVP Approach:
- Manual booking process
- WhatsApp/Kakao for communication
- Google Forms for payment
- Spreadsheet for management

Tech Investment: Phase 1
- After validation
- 500만원 = 2 developer weeks

✅ Updated mvp-scope.md
```

---

## Key Principles

### MVP 원칙:

1. **Maximize Learning**: 최소 투자로 최대 학습
2. **Ship Fast**: 완벽보다 속도
3. **Core Value Only**: 핵심 가치만 구현
4. **Real Users**: 실제 사용자로 검증
5. **Metrics-Driven**: 감이 아닌 데이터로 결정

### MVP Anti-Patterns:

❌ **Feature Creep**: "이것도 있으면 좋겠는데..."
❌ **Perfectionism**: "조금만 더 다듬고..."
❌ **Assumption**: "사용자는 당연히..."
❌ **Vanity Metrics**: 의미 없는 지표 추적
❌ **Premature Scaling**: 검증 전 확장

---

## Tips

### 성공적인 MVP를 위해:

1. **Time Box**: 2주를 넘기지 마라
2. **User Cap**: 10-100명으로 시작
3. **Manual First**: 자동화는 나중에
4. **Talk to Users**: 매일 사용자와 대화
5. **Kill Features**: 과감하게 빼라

### MVP 실패 신호:

- 2주 지나도 출시 못함
- 기능이 계속 추가됨
- 사용자 피드백 없음
- 지표 측정 안 함
- "좀 더 완벽하게" 반복

---

## Next Steps

### 이 명령어 실행 후:

**📍 다음 단계: Step 6 - `/appkit.merge`** (기획 정돈)
- MVP 범위가 정해졌으니 이제 기획 정돈 단계로
- 용어 통일, 기능 중복 제거
- 고객 가치 일관성 확보

---

## Version

- **Version**: 1.0.0
- **Created**: 2025-11-19
- **Philosophy**: "If you're not embarrassed by v1, you launched too late"