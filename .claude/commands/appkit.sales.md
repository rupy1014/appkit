# appkit.sales

**고객을 설득하는 세일즈 랜딩 메시지를 구성하는 명령어**

---

## Overview

**This is Step 4 of the logical thinking 7-step workflow**:

```
논리적 사고 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?) ← YOU ARE HERE
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

## Purpose

타겟 고객의 문제와 욕구를 기반으로 설득력 있는 세일즈 메시지를 구성합니다.
기능 나열이 아닌, 고객 가치와 변화 스토리로 설득합니다.

**핵심 질문**: "어떻게 고객을 설득할까?"

---

## When to Use

- `/appkit.customer`로 타겟 고객을 정의한 후 (Step 3 완료 후)
- 랜딩 페이지나 마케팅 메시지가 필요할 때
- 투자자나 팀에게 가치 제안을 설명할 때
- MVP 출시 전 메시지 테스트가 필요할 때

---

## Usage

```bash
/appkit.sales
/appkit.sales "time-saving for busy professionals"
/appkit.sales "price-sensitive students"
/appkit.sales "landing: premium positioning"
```

---

## What I'll Do

### 1. 세일즈 프레임워크 선택

**상황별 최적 프레임워크**:

```markdown
## Framework Selection

### PAS (Problem-Agitate-Solution)
✅ Best for: 명확한 문제가 있는 경우
- Problem: 고객이 겪는 문제 공감
- Agitate: 문제를 더 심각하게 느끼게
- Solution: 우리 서비스가 해결책

### AIDA (Attention-Interest-Desire-Action)
✅ Best for: 새로운 카테고리 창출
- Attention: 놀라운 통계나 질문
- Interest: 흥미로운 가능성 제시
- Desire: 갖고 싶게 만들기
- Action: 지금 행동하게 만들기

### StoryBrand
✅ Best for: 복잡한 서비스 설명
- Character: 고객이 주인공
- Problem: 겪고 있는 문제
- Guide: 우리가 안내자
- Plan: 명확한 해결 단계
- Success: 성공 스토리
```

### 2. 랜딩 페이지 구조 (PAS 기준)

```markdown
## Landing Page Structure

### 1️⃣ Hero Section (Hook - 3초 승부)
---
[Headline - 핵심 가치]
"테니스 코트 예약, 이제 3초면 충분합니다"

[Subheadline - 구체적 혜택]
"전화 대기 없이, 실시간 예약, 자동 할인까지"

[CTA Button]
"지금 시작하기 →"

[Hero Image]
스마트폰으로 예약하는 모습


### 2️⃣ Problem Section (공감대 형성)
---
"이런 경험, 해보셨나요?"

❌ 전화 예약하려다 15분 대기
❌ 원하는 시간대는 항상 만석
❌ 가격 비교는 불가능
❌ 취소하려면 또 전화

"매주 테니스 치고 싶은데,
예약이 너무 번거로워 포기하신 적 있으시죠?"


### 3️⃣ Agitation Section (문제 심화)
---
[통계로 문제 심화]
"직장인 73%가 운동 부족"
"운동 포기 이유 1위: 번거로운 예약(42%)"

[감정 자극]
"주말마다 '이번엔 꼭 운동해야지' 다짐하지만,
복잡한 예약 과정에 지쳐 결국 포기하고 있지 않나요?"


### 4️⃣ Solution Section (해결책 제시)
---
"3초 예약 시스템"

[Step 1] 📍 위치 선택
가까운 코트 자동 추천

[Step 2] 📅 시간 선택
실시간 예약 가능 시간 확인

[Step 3] 💳 결제 완료
원터치 결제, 자동 할인 적용

"복잡한 과정은 우리가 해결했습니다"


### 5️⃣ Benefits Section (구체적 혜택)
---
[시간 절약]
⏰ 평균 15분 → 3초
"매주 1시간 절약"

[비용 절감]
💰 자동 할인 적용
"평균 30% 저렴"

[편의성]
📱 언제 어디서나
"지하철에서도 예약 가능"


### 6️⃣ Social Proof Section (신뢰 구축)
---
[숫자로 증명]
"5,000명이 매주 사용 중"
"월 10,000건 예약 처리"
"평균 평점 4.8/5.0"

[고객 후기]
"김OO (37세, 직장인)"
"퇴근길 지하철에서 예약 완료!
주말 운동이 규칙적으로 바뀌었어요"

"박OO (29세, 프리랜서)"
"평일 낮 할인으로 30% 절약!
시간도 자유롭고 가격도 저렴해요"


### 7️⃣ CTA Section (행동 유도)
---
[긴급성 생성]
"🎁 지금 가입하면 첫 예약 30% 할인"
"⏰ 이번 주말 예약 마감 임박"

[3단계 CTA]
1. "무료로 시작하기" (부담 제거)
2. "1분 만에 가입" (간편함 강조)
3. "첫 예약 30% 할인" (즉각 혜택)

[보증]
"예약 수수료 없음"
"언제든 취소 가능"
```

### 3. 가치 제안 캔버스 (Value Proposition Canvas)

```markdown
## Value Proposition

### Customer Jobs (고객이 해결하려는 일)
- 주말 운동 계획
- 건강 관리
- 스트레스 해소
- 사회적 교류

### Pain Relievers (고통 해결)
- 전화 대기 → 즉시 예약
- 불확실성 → 실시간 확인
- 비싼 가격 → 자동 할인
- 복잡한 과정 → 3단계 간소화

### Gain Creators (이익 창출)
- 시간 절약 (주당 1시간)
- 비용 절감 (30% 할인)
- 규칙적 운동 습관
- 운동 仲間 찾기
```

### 4. 메시지 A/B 테스트 제안

```markdown
## A/B Testing Suggestions

### Headline Variations
A: "테니스 코트 예약, 이제 3초면 충분합니다"
B: "매주 테니스 치고 싶다면? 앱으로 3초 예약"
C: "전화 대기는 그만, 실시간 코트 예약"

### CTA Variations
A: "지금 시작하기"
B: "무료로 예약하기"
C: "30% 할인받기"

### Value Prop Variations
A: "시간 절약" 중심
B: "비용 절감" 중심
C: "편의성" 중심
```

### 5. 채널별 메시지 최적화

```markdown
## Channel-Specific Messages

### Instagram Ad (비주얼 중심)
[Image: 테니스 치는 행복한 모습]
"주말 테니스, 3초 예약 ✨"
#테니스 #주말운동 #코트예약

### Google Ads (검색 의도 명확)
"테니스 코트 예약 | 실시간 예약 | 30% 할인"
"전화 대기 없이 바로 예약. 지금 시작하기"

### Email (스토리텔링)
Subject: "김대리님, 이번 주말 테니스 어떠세요?"
"매번 예약 때문에 포기하셨다면..."
[Full story + CTA]

### 카톡 채널 (친근한 톤)
"테니스 예약 때문에 스트레스 받으셨죠? 😅
이제 카톡하듯 쉽게 예약하세요!"
```

---

## Output Files

### 생성될 파일들:

1. **`docs/appkit/sales-landing.md`**
   - 전체 랜딩 페이지 구조
   - 섹션별 메시지
   - CTA 전략

2. **`docs/appkit/value-proposition.md`**
   - 핵심 가치 제안
   - Pain-Gain 매트릭스
   - 차별화 포인트

---

## Integration Points

### 다른 명령어와의 연계:

- **From `/appkit.customer`**: 페르소나별 Pain Points
- **From `/appkit.spec`**: 핵심 기능과 혜택
- **To `/appkit.mvp`**: 검증할 핵심 가치
- **To `/appkit.design`**: 사용자 온보딩 플로우

---

## Examples

### Example 1: B2C 서비스
```bash
$ /appkit.sales

📢 Sales Landing Generated

Framework: PAS (Problem-Agitate-Solution)

Hero: "3초 예약 혁명"
Problem: 복잡한 예약 과정
Agitate: 73% 운동 포기
Solution: 원터치 시스템
Proof: 5,000명 사용 중
CTA: "지금 30% 할인"

✅ Generated sales-landing.md
✅ Generated value-proposition.md
```

### Example 2: 특정 페르소나 타겟
```bash
$ /appkit.sales "price-sensitive students"

📢 Student-Focused Message

Hero: "학생 90% 할인"
Problem: 비싼 코트 가격
Solution: 그룹 예약 할인
Proof: "서울대 테니스 동아리 공식 앱"
CTA: "학생증 인증하고 90% 할인"

✅ Updated sales-landing.md
```

---

## Key Principles

### 세일즈 메시지 원칙:

1. **Features ❌ Benefits ✅**: "실시간 예약"이 아닌 "대기 시간 제로"
2. **You, not We**: "당신은" 중심, "우리는" 최소화
3. **Specific Numbers**: "많이"가 아닌 "73%"
4. **Emotional + Rational**: 감정 자극 + 논리적 근거
5. **Clear Next Step**: 모호한 CTA는 전환율 킬러

---

## Tips

### 고전환율 랜딩 페이지:

1. **Above the Fold**: 스크롤 없이 핵심 가치 전달
2. **One Message**: 한 페이지, 하나의 메시지
3. **Social Proof**: 숫자 > 로고 > 후기 순으로 배치
4. **Urgency**: "지금" 행동해야 할 이유
5. **Risk Reversal**: 무료 체험, 환불 보장

### 카피라이팅 공식:

- **Headline**: 혜택 + 숫자 + 시간
- **CTA**: 동사 + 혜택 + 긴급성
- **Testimonial**: 이름 + 나이 + 직업 + 구체적 결과

---

## Next Steps

### 이 명령어 실행 후:

**📍 다음 단계: Step 5 - `/appkit.mvp`** (MVP 범위 정의)
- 세일즈 메시지에서 약속한 핵심 가치만 구현
- 최소한의 기능으로 시장 검증

---

## Version

- **Version**: 1.0.0
- **Created**: 2025-11-19
- **Philosophy**: "Sell the hole, not the drill"