# appkit.customer

**타겟 고객을 명확히 하고 그들의 스토리를 구성하는 명령어**

---

## Overview

**This is Step 3 of the logical thinking 7-step workflow**:

```
논리적 사고 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결) ← YOU ARE HERE
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

## Purpose

타겟 고객을 구체화하고 그들의 일상과 문제를 스토리텔링으로 풀어내어,
서비스가 어떤 가치를 제공하는지 명확히 합니다.

**핵심 질문**: "누가, 왜 이 서비스를 쓸까?"

---

## When to Use

- `/appkit.spec`으로 기능들을 구체화한 후 (Step 2 완료 후)
- 타겟 고객이 여전히 모호할 때
- 고객의 구체적인 사용 시나리오가 필요할 때
- 세일즈 메시지 작성 전 고객 이해가 필요할 때

---

## Usage

```bash
/appkit.customer
/appkit.customer "30대 직장인 주말 운동"
/appkit.customer "persona: busy professional"
/appkit.customer "journey: from problem to solution"
```

---

## What I'll Do

### 1. 고객 페르소나 구성 (Customer Persona)

**Primary Persona** (주요 고객):
```markdown
## Primary Persona: [이름] ([나이], [직업])

### Demographics (인구통계)
- 나이: 30-40대
- 직업: IT 기업 직장인
- 소득: 연 5000-8000만원
- 거주지: 서울/경기 아파트
- 가족: 기혼, 자녀 1-2명

### Psychographics (심리/행동)
- 라이프스타일: 워라밸 추구, 건강 관심 증가
- 가치관: 시간 효율성, 편의성 중시
- 관심사: 주말 운동, 가족과 시간
- 기술 친숙도: 높음, 모바일 앱 일상화

### Pain Points (현재 고민)
1. 운동하고 싶은데 시간이 없다
2. 코트 예약이 너무 번거롭다
3. 원하는 시간대는 항상 만석
4. 가격 비교가 어렵다

### Goals (달성하고 싶은 것)
- 규칙적인 주말 운동
- 스트레스 없는 예약 과정
- 합리적인 가격으로 운동
- 가족/친구와 함께하는 시간
```

**Secondary Personas** (보조 고객):
- 프리랜서 (시간 유연, 가격 민감)
- 대학생 (저렴한 가격 선호)
- 주부 (평일 낮 시간 활용)

### 2. 고객 여정 맵 (Customer Journey Map)

**하루의 스토리텔링**:

```markdown
## 김대리의 하루 (현재 - Problem State)

### 평일
07:00 😴 "오늘도 운동 못하겠네..." (죄책감)
08:30 🚇 지하철에서 "주말엔 꼭 테니스 쳐야지" (다짐)
12:00 🍽️ 점심시간 "코트 예약하려니... 전화해야 하나?" (귀찮음)
15:00 ☎️ "예약 전화... 통화중이네" (짜증)
18:00 😔 "주말 코트 다 찼대..." (실망)
21:00 🏠 "내일 아침 일찍 전화해볼까?" (미룸)

### 주말
토요일 오전 - 결국 운동 못함
일요일 - 가족과 시간 보내느라 포기

---

## 김대리의 하루 (미래 - Solution State)

### 평일
07:00 📱 침대에서 앱 열기 (3초)
07:01 ✅ "토요일 오전 10시 예약 완료!" (만족)
12:00 💰 "타임딜 30% 할인 알림" (기쁨)
18:00 👥 "동료들도 같이 예약할까?" (공유)

### 주말
토요일 10:00 - 테니스 코트에서 운동 중
토요일 12:00 - "운동 후 상쾌해!" (성취감)
일요일 - 가족과 여유롭게 시간 보내기
```

### 3. 문제-해결 시나리오

**Before (현재 상황)**:
```
1. 예약하려면 → 전화해야 함 (15분 대기)
2. 가격 확인 → 일일이 물어봐야 함
3. 시간대 확인 → 전화로만 가능
4. 취소/변경 → 또 전화
5. 결과 → 포기하거나 비싼 값 지불
```

**After (서비스 사용 후)**:
```
1. 예약 → 앱에서 3초 (실시간)
2. 가격 → 한눈에 비교 (투명)
3. 시간대 → 달력으로 확인 (직관적)
4. 취소/변경 → 클릭 한 번 (간편)
5. 결과 → 규칙적 운동 + 30% 절약
```

### 4. 감정 곡선 (Emotional Journey)

```
현재 경험:
기대 → 검색 → 좌절 → 포기
😊 → 😐 → 😤 → 😔

서비스 경험:
발견 → 시도 → 성공 → 만족 → 추천
😐 → 😊 → 😃 → 😍 → 🎉
```

### 5. 고객 인사이트 도출

**핵심 인사이트**:
1. **시간이 돈보다 중요**: 15분 기다리느니 조금 더 내고 앱 사용
2. **즉시성 중요**: "지금 당장" 예약 확정 받고 싶음
3. **투명성 요구**: 가격, 시간, 위치 한번에 보고 싶음
4. **Social Proof**: 다른 사람들도 쓰는지 궁금
5. **습관 형성**: 규칙적 운동을 원하지만 예약이 방해물

---

## Output Files

### 생성될 파일들:

1. **`docs/appkit/customer-persona.md`**
   - Primary & Secondary 페르소나
   - Demographics & Psychographics
   - Pain Points & Goals

2. **`docs/appkit/customer-journey.md`**
   - 현재 vs 미래 하루 스토리
   - 감정 곡선
   - 터치포인트 분석
   - 기회 영역 식별

---

## Integration Points

### 다른 명령어와의 연계:

- **From `/appkit.spec`**: 기능별 사용자 프로파일 수집
- **To `/appkit.sales`**: 페르소나별 메시지 구성
- **To `/appkit.mvp`**: 핵심 고객의 핵심 문제 우선 해결
- **To `/appkit.design`**: 사용자 플로우 설계 기초

---

## Examples

### Example 1: 테니스 예약 앱
```bash
$ /appkit.customer

🎯 Target Customer Analysis

Primary: 30-40대 직장인
- Pain: 전화 예약 번거로움
- Want: 빠른 예약, 주말 운동
- Value: 시간 절약 > 비용 절약

Journey Highlights:
- Morning: 운동 계획 (의지)
- Lunch: 예약 시도 (좌절)
- Evening: 포기 (실망)
- Weekend: 운동 못함 (죄책감)

Key Insight:
"예약 friction이 운동 의지를 꺾는다"

✅ Generated customer-persona.md
✅ Generated customer-journey.md
```

### Example 2: 추가 페르소나 정의
```bash
$ /appkit.customer "freelancer flexible schedule"

🎯 Secondary Persona Added

프리랜서 (28세):
- Pain: 비싼 prime time 가격
- Want: 평일 낮 할인
- Value: 가격 > 시간대

Opportunity:
"평일 낮 유휴 시간 + 가격 민감 고객 매칭"

✅ Updated customer-persona.md
```

---

## Key Principles

### 고객 이해의 원칙:

1. **공감 먼저, 기능 나중**: 고객의 감정을 이해하라
2. **구체적 스토리**: "30대 직장인"이 아닌 "김대리의 하루"
3. **Before/After 대비**: 변화를 명확히 보여주기
4. **감정 추적**: 각 단계에서 고객이 느끼는 감정
5. **인사이트 도출**: 데이터가 아닌 행동 패턴 발견

---

## Tips

### 효과적인 페르소나 작성:

1. **이름을 붙여라**: "User A"가 아닌 "김대리"
2. **하루를 그려라**: 아침부터 저녁까지 구체적으로
3. **감정을 표현하라**: 😊😔😤 이모지 활용
4. **대화체 사용**: "아, 또 만석이네..." 실제 혼잣말
5. **숫자로 구체화**: "많이"가 아닌 "15분 대기"

---

## Next Steps

### 이 명령어 실행 후:

**📍 다음 단계: Step 4 - `/appkit.sales`** (세일즈 랜딩 구성)
- 고객 페르소나와 스토리를 기반으로 설득 메시지 작성
- 고객의 문제와 해결책을 중심으로 구성

---

## Version

- **Version**: 1.0.0
- **Created**: 2025-11-19
- **Philosophy**: "기능이 아닌 고객의 삶을 디자인하라"