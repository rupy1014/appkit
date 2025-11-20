# market.customer

**MVP에 맞는 타겟 고객 세분화 및 채널 추천 명령어**

---

## Overview

**This is the first step of the 4C Marketing Framework**:

```
저비용 마케팅 4C:
1. /market.customer    → 고객 세분화 & 채널 추천 (누구에게, 어디서?) ← YOU ARE HERE
2. /market.contents    → 콘텐츠 전략 & 재활용 (무엇을 만들까?)
3. /market.channel     → 채널별 최적화 전략 (어떻게 최적화할까?)
4. /market.communicate → 바이럴 & 커뮤니티 전략 (어떻게 퍼뜨릴까?)
```

## Purpose

MVP 제품의 특성을 분석하여 **가장 효과적인 타겟 고객 세그먼트**를 찾고,
그들이 실제로 있는 **채널**을 추천합니다.

**핵심 질문**: "누가 가장 먼저 우리 제품을 써줄까? 그들은 지금 어디 있을까?"

---

## When to Use

- `/appkit.mvp`로 MVP 범위를 정의한 후
- 제품 출시 전 마케팅 전략 수립 시
- 광고비 없이 초기 고객을 확보해야 할 때
- 채널 선택이 불명확할 때

---

## Usage

```bash
/market.customer
/market.customer "테니스 코트 예약 앱"
/market.customer "직장인 대상 SaaS 툴"
```

---

## What I'll Do

### 1. 제품 맥락 분석

```markdown
## Product Context Analysis

### Input Sources
- `docs/appkit/overview.md` → 서비스 본질 파악
- `docs/appkit/customer-persona.md` → 기존 페르소나 활용
- `docs/appkit/mvp-scope.md` → MVP 핵심 가치 확인

### Key Questions
- 이 제품은 무엇을 해결하는가?
- 가장 급한 문제를 가진 사람은 누구인가?
- 돈을 낼 만한 가치가 있는 사람은?
- 입소문을 낼 만한 사람은?
```

### 2. 고객 세그먼트 우선순위화

```markdown
## Customer Segmentation Matrix

### Early Adopters (최우선 타겟)
"제품이 완벽하지 않아도 먼저 써줄 사람들"

#### Segment 1: 테니스 동호회 운영진 (Primary)
**Why First?**
- Pain Point 강도: ⭐⭐⭐⭐⭐ (매주 예약 전화 30통)
- 구매력: ⭐⭐⭐⭐ (회비로 결제 가능)
- 입소문 파급력: ⭐⭐⭐⭐⭐ (회원 20-50명에게 즉시 전파)
- 접근 용이성: ⭐⭐⭐⭐ (네이버 카페, 밴드에 집중)

**Demographics**
- 나이: 35-55세
- 직업: 회사원, 자영업
- 소득: 중상위
- 지역: 수도권

**Psychographics**
- 가치관: "우리 회원들 편하게 해주고 싶다"
- 관심사: 동호회 활성화, 효율적 운영
- 정보 습득: 네이버 카페, 밴드, 카톡 단톡방
- 구매 결정: 실용성 > 가격 (회원들이 좋아하면 OK)

**Where Are They?**
1. 네이버 카페: "테니스 동호회", "XX지역 테니스"
2. 밴드: 지역별 테니스 밴드
3. 카카오톡: 동호회 단톡방 (접근 어려움)
4. 오프라인: 주말 아침 코트장

**First Touch Strategy**
→ 네이버 카페 "운영진 고민" 게시판에 진짜 경험담 작성
→ "저희 동호회 예약 관리 이렇게 해결했어요" (광고 X)


#### Segment 2: 직장 내 테니스 동아리 간사 (Secondary)
**Why Second?**
- Pain Point: ⭐⭐⭐⭐ (분기별 예약 업무 스트레스)
- 구매력: ⭐⭐⭐ (동아리 예산 있음)
- 입소문: ⭐⭐⭐ (다른 직장 동아리로 전파 가능)
- 접근: ⭐⭐⭐ (링크드인, 직장인 커뮤니티)

**Where Are They?**
1. 블라인드: "직장 생활" 게시판
2. 링크드인: 직장인 그룹
3. 사내 게시판: 접근 어려움
4. 오픈 채팅방: "XX기업 테니스"


#### Segment 3: 개인 열성 플레이어 (Tertiary)
**Why Third?**
- Pain Point: ⭐⭐⭐ (개인 예약 번거로움)
- 구매력: ⭐⭐⭐⭐ (개인 결제)
- 입소문: ⭐⭐ (개인적 추천)
- 접근: ⭐⭐⭐⭐⭐ (인스타, 유튜브)

**Where Are They?**
1. 인스타그램: #테니스 #테린이 #테니스레슨
2. 유튜브: 테니스 레슨 영상 댓글란
3. 테니스용품 쇼핑몰: 커뮤니티 게시판
```

### 3. Channel Recommendation Matrix

```markdown
## Channel Priority by Customer Segment

### Tier 1: Immediate Action (이번 주부터)
"Early Adopters가 있는 곳"

| Channel | Segment | Cost | Effort | Expected Result |
|---------|---------|------|--------|-----------------|
| 네이버 카페 | 동호회 운영진 | 무료 | 중 | 첫 10명 확보 |
| 밴드 | 동호회 | 무료 | 중 | 첫 단체 고객 |
| 블라인드 | 직장 동아리 | 무료 | 하 | 피드백 수집 |

**Action Plan (Week 1-2)**
1. 네이버 카페 10개 가입
   - "서울 테니스 동호회"
   - "경기 테니스 모임"
   - "주말 테니스"
2. 운영진 고민 게시판에 진짜 경험담 작성
3. DM으로 베타 테스터 모집 (광고 아님)


### Tier 2: Medium-term Growth (2-4주)
"인지도 확산"

| Channel | Segment | Cost | Effort | Expected Result |
|---------|---------|------|--------|-----------------|
| 인스타그램 | 개인 플레이어 | 저 | 중 | 브랜드 인지도 |
| 유튜브 쇼츠 | 일반 대중 | 저 | 고 | 자연 유입 |
| 블로그 SEO | 검색 유입 | 무료 | 중 | 장기 자산 |

**Content Ideas**
- 인스타 릴스: "테니스 코트 예약 꿀팁"
- 유튜브 쇼츠: "동호회 총무가 알려주는 예약 비법"
- 블로그: "서울 테니스 코트 예약 가이드"


### Tier 3: Scale (4주+)
"매스 마케팅 준비"

| Channel | Segment | Cost | Effort | Expected Result |
|---------|---------|------|--------|-----------------|
| 네이버 광고 | 검색 유입 | 중 | 하 | 빠른 확장 |
| 인플루언서 | 대중 | 중-고 | 중 | 바이럴 |
| 제휴 (코트) | 장소 기반 | 무료 | 고 | Win-win |

**Note**: Tier 3는 Tier 1-2 검증 후 진행
```

### 4. Persona-Channel-Message Mapping

```markdown
## Integrated Marketing Map

### Early Adopter Journey

#### Persona: 김회장 (45세, 테니스 동호회 회장)

**현재 상황**
- 매주 토요일 아침 예약을 위해 5개 코트에 전화
- 회원 25명 일정 조율이 가장 큰 스트레스
- 네이버 카페에서 "이번 주 예약 완료" 공지 작성

**Where**: 네이버 카페 "서울 테니스 동호회" (회원 3,500명)

**Message Hook**:
"동호회 회장님들, 매주 코트 예약 전화 30통 거는 거 지치지 않으세요?"

**Offer**:
"저희 동호회는 이 앱으로 예약 관리 10분으로 줄였습니다"
→ 무료 베타 테스터 모집 (선착순 10개 동호회)

**Conversion Path**:
1. 카페 게시글 작성 (진짜 경험담)
2. 댓글로 문의 → DM으로 안내
3. 카톡 오픈채팅방 초대
4. 사용 가이드 제공
5. 후기 작성 부탁 (인센티브: 1개월 무료)


#### Persona: 박간사 (32세, 직장 테니스 동아리 간사)

**Where**: 블라인드 "직장 생활" 게시판

**Message Hook**:
"테니스 동아리 간사 맡았다가 예약 업무로 퇴근 늦어본 적 있으신가요?"

**Offer**:
"3분 만에 분기 예약 완료하는 법"
→ 체크리스트 PDF 다운로드 (이메일 수집)

**Conversion Path**:
1. 블라인드 게시글
2. PDF 다운로드 (랜딩 페이지)
3. 이메일로 앱 소개
4. 7일 무료 체험
```

### 5. Channel Testing Framework

```markdown
## Channel Validation Checklist

### Week 1-2: Hypothesis Testing
각 채널에서 최소 실험 진행

#### Test 1: 네이버 카페
**Hypothesis**: 동호회 운영진이 실제 사용할까?

**Experiment**:
- 5개 카페에 경험담 게시
- 베타 테스터 10명 모집 목표

**Success Metrics**:
- 게시글 조회수: 500+
- DM 문의: 5+
- 실제 가입: 3+

**Pivot Signal**:
- 조회수 < 100: 메시지 변경
- 문의 < 2: 채널 변경


#### Test 2: 블라인드
**Hypothesis**: 직장인들이 관심 가질까?

**Experiment**:
- "직장 생활" 게시판 2건 작성
- PDF 다운로드 20건 목표

**Success Metrics**:
- 공감 수: 10+
- 댓글: 5+
- PDF 다운로드: 20+

**Pivot Signal**:
- 공감 < 5: 타겟 불일치
- 다운로드 < 5: 오퍼 변경


### Week 3-4: Double Down
검증된 채널에 집중

**If 네이버 카페 wins**:
→ 10개 → 30개 카페로 확대
→ 성공 사례 스토리텔링

**If 블라인드 wins**:
→ 다른 직장인 커뮤니티 확대 (당근 동네생활, 에브리타임)
```

---

## Output Files

### 생성될 파일들:

1. **`docs/market/customer-segments.md`**
   - Early Adopter 우선순위
   - 세그먼트별 특성 및 Pain Point
   - Where they are (구체적 채널)

2. **`docs/market/channel-recommendations.md`**
   - Tier 1/2/3 채널 우선순위
   - 채널별 비용/노력/기대효과
   - 주차별 실행 계획

3. **`docs/market/persona-channel-map.md`**
   - 페르소나별 고객 여정
   - 채널-메시지 매칭
   - 전환 경로 설계

---

## Integration Points

### 다른 명령어와의 연계:

- **From `/appkit.customer`**: Primary Persona 활용
- **From `/appkit.mvp`**: MVP 핵심 가치 → 메시지 훅
- **To `/market.contents`**: 채널별 콘텐츠 아이디어
- **To `/market.channel`**: 선택된 채널의 최적화 전략

---

## Examples

### Example 1: B2C 모바일 앱
```bash
$ /market.customer "테니스 코트 예약 앱"

🎯 Customer Segmentation Complete

Early Adopters (우선순위):
1. 테니스 동호회 운영진 (Primary)
   → 네이버 카페, 밴드
2. 직장 테니스 동아리 간사 (Secondary)
   → 블라인드, 링크드인
3. 개인 열성 플레이어 (Tertiary)
   → 인스타그램, 유튜브

Tier 1 Channels (이번 주):
✅ 네이버 카페 10개
✅ 밴드 5개
✅ 블라인드 "직장생활"

Week 1-2 Goal:
- 첫 10명 Early Adopters 확보
- 채널별 A/B 테스트
- 검증된 채널에 집중

✅ Generated customer-segments.md
✅ Generated channel-recommendations.md
✅ Generated persona-channel-map.md
```

### Example 2: B2B SaaS 툴
```bash
$ /market.customer "직장인 일정 관리 SaaS"

🎯 Customer Segmentation Complete

Early Adopters:
1. 스타트업 팀장 (5-10명 팀)
   → 링크드인, 스타트업 커뮤니티
2. 프리랜서 PM/기획자
   → 브런치, 퍼블리

Tier 1 Channels:
✅ 링크드인 (전문가 네트워킹)
✅ 디스콰이엇 (스타트업)
✅ 브런치 (콘텐츠 마케팅)

Week 1-2 Goal:
- 베타 고객 5팀 확보
- 사용 사례 확보
- 추천 바이럴 유도

✅ Generated files
```

---

## Key Principles

### Customer-First Marketing:

1. **Segment Before Scale**: 대중보다 틈새 시장 먼저
2. **Go Where They Are**: 새 채널 만들지 말고 기존 공간에 들어가기
3. **Earn Trust First**: 광고하지 말고 진짜 가치 제공
4. **Manual Initially**: 자동화 전에 직접 대화
5. **Quality > Quantity**: 1000명보다 진짜 좋아하는 10명

### Channel Anti-Patterns:

❌ **Spray and Pray**: 모든 채널 동시 시도
❌ **Vanity Metrics**: 팔로워 수에 집착
❌ **Ad Dependence**: 광고비 없으면 고객 못 모으는 구조
❌ **Broadcasting**: 일방적 홍보
❌ **Impatience**: 첫 주에 결과 기대

---

## Tips

### 성공적인 Early Adopter 확보를 위해:

1. **Micro-Segment**: 작고 구체적인 세그먼트부터
   - "테니스 좋아하는 사람" ❌
   - "주말 아침 테니스 동호회 운영진" ✅

2. **Real Pain Only**: 진짜 아픈 문제만 타겟
   - "있으면 좋을 것 같은데" ❌
   - "이거 없으면 진짜 힘들어" ✅

3. **Community First**: 개인보다 커뮤니티
   - 개인 1명 전환 < 동호회 회장 1명 전환 (20명 동반)

4. **Earn Your Way In**: 스팸하지 말고 신뢰 쌓기
   - "우리 제품 써주세요" ❌
   - "제가 이런 고민 해결했는데 도움 될까요?" ✅

5. **Test Fast, Pivot Faster**: 2주 안에 검증
   - 반응 없으면 과감히 채널/메시지 변경

---

## Next Steps

### 이 명령어 실행 후:

**📍 다음 단계: `/market.contents`** (콘텐츠 전략)
- 타겟 채널이 정해졌으니 어떤 콘텐츠를 만들지 기획
- 하나의 핵심 메시지를 10가지 포맷으로 재활용
- 채널별 최적 콘텐츠 형식 제안

---

## Version

- **Version**: 1.0.0
- **Created**: 2025-11-20
- **Philosophy**: "Find the smallest viable audience that loves you, not the largest possible audience that's indifferent."
