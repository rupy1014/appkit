# AppKit - AI 기획 도우미

AppKit은 막연한 아이디어를 실행 가능한 기획으로 구체화하는 7단계 논리적 사고 프레임워크입니다.

## 🎯 AppKit이란?

AppKit은 서비스 기획의 전 과정을 체계적으로 안내하는 Claude Code 커맨드 세트입니다.
"이런 앱 만들면 좋을 것 같은데..."라는 막연한 생각부터 개발팀에게 전달할 수 있는 구체적인 기술 스펙까지, 단계별로 문서를 생성하며 기획을 완성해갑니다.

## 🤔 왜 AppKit을 사용하나요?

### 기획할 때 이런 어려움 겪지 않으셨나요?

- "좋은 아이디어가 있는데 어떻게 시작해야 할지 모르겠어요"
- "기능은 많이 생각했는데, 정작 고객이 누군지 모호해요"
- "MVP로 뭘 만들어야 할지 우선순위를 못 정하겠어요"
- "개발자에게 뭘 전달해야 할지 막막해요"

AppKit은 이런 문제를 7단계로 나누어 하나씩 해결합니다.

## 📋 7단계 워크플로우

AppKit은 논리적 사고의 흐름에 따라 7단계로 구성됩니다:

```
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합)
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

각 단계는 독립적으로 사용할 수도 있지만, 순서대로 진행하면 가장 체계적인 기획이 완성됩니다.

---

## 📖 각 커맨드 상세 설명

### 1️⃣ `/appkit.new` - 아이디어 스케치

**언제 사용하나요?**
- 프로젝트를 처음 시작할 때
- 막연한 아이디어를 구체화하고 싶을 때

**무엇을 하나요?**
- 자연어로 입력한 아이디어를 분석합니다
- 핵심 문제와 해결책을 정리합니다
- 타겟 고객을 추론합니다
- 주요 기능 목록을 도출합니다

**사용 예시:**
```bash
/appkit.new 테니스 코트 예약 앱. 실시간 예약과 할인 쿠폰 기능 포함
```

**생성되는 파일:**
- `docs/appkit/overview.md` - 서비스 컨셉 문서
- `docs/appkit/specs/001-xxx/spec.md` - 각 기능별 초안

---

### 2️⃣ `/appkit.spec` - 기능 구체화

**언제 사용하나요?**
- 각 기능을 더 상세하게 정의하고 싶을 때
- 사용자 시나리오를 추가하고 싶을 때

**무엇을 하나요?**
- 자연어 입력을 분석하여 spec 문서에 추가합니다
- 사용자 여정(User Journey)을 구체화합니다
- 비즈니스 룰과 엣지 케이스를 정리합니다
- 점진적으로 내용을 추가해갑니다 (이전 내용 보존)

**사용 예시:**
```bash
/appkit.spec 001-search "위치 기반으로 가까운 코트 찾기, 거리순 정렬"
/appkit.spec 002-booking "퇴근길 지하철에서 3초 예약, 원터치 결제"
```

**특징:**
- 한 번에 완벽하게 작성할 필요 없습니다
- 여러 번 실행하며 점진적으로 디테일을 추가합니다
- 이전 내용은 보존하고 새 내용만 추가됩니다

---

### 3️⃣ `/appkit.customer` - 고객 스토리

**언제 사용하나요?**
- 타겟 고객을 명확히 하고 싶을 때
- 고객의 문제를 깊이 이해하고 싶을 때
- 마케팅이나 세일즈 메시지 준비 전

**무엇을 하나요?**
- Primary/Secondary 페르소나를 생성합니다
- 고객의 하루를 스토리텔링으로 풀어냅니다
- Before/After 대비로 변화를 보여줍니다
- Pain Points와 Goals를 명확히 합니다

**사용 예시:**
```bash
/appkit.customer
/appkit.customer "30대 직장인 주말 운동"
```

**생성되는 파일:**
- `docs/appkit/customer-persona.md` - 타겟 고객 페르소나
- `docs/appkit/customer-journey.md` - 고객 여정 맵

---

### 4️⃣ `/appkit.sales` - 세일즈 랜딩

**언제 사용하나요?**
- 랜딩 페이지나 마케팅 메시지가 필요할 때
- 고객을 설득하는 방법을 고민할 때
- MVP 출시 전 메시지 테스트가 필요할 때

**무엇을 하나요?**
- PAS, AIDA 등 검증된 세일즈 프레임워크를 적용합니다
- Hero, Problem, Solution 섹션을 구성합니다
- CTA(Call-to-Action) 전략을 제시합니다
- 채널별 메시지 최적화 방안을 제안합니다

**사용 예시:**
```bash
/appkit.sales
/appkit.sales "time-saving for busy professionals"
```

**생성되는 파일:**
- `docs/appkit/sales-landing.md` - 랜딩 페이지 구조
- `docs/appkit/value-proposition.md` - 핵심 가치 제안

---

### 5️⃣ `/appkit.mvp` - MVP 범위 정하기

**언제 사용하나요?**
- 개발 시작 전 범위를 정해야 할 때
- 리소스가 제한적일 때
- 빠른 시장 검증이 필요할 때

**무엇을 하나요?**
- Phase 0(핵심 MVP), Phase 1, Phase 2로 기능을 분류합니다
- Must Have / Should Have / Nice to Have를 구분합니다
- 성공 지표와 검증 기준을 설정합니다
- 2주 안에 실행 가능한 범위로 압축합니다

**사용 예시:**
```bash
/appkit.mvp
/appkit.mvp "2-week validation"
/appkit.mvp "budget: 500만원"
```

**생성되는 파일:**
- `docs/appkit/mvp-scope.md` - MVP 범위 정의
- `docs/appkit/mvp-metrics.md` - 검증 지표

---

### 6️⃣ `/appkit.merge` - 기획 정돈

**언제 사용하나요?**
- MVP 범위를 정한 후
- 여러 문서 간 중복이나 충돌이 보일 때
- 개발 시작 전 기획을 정리하고 싶을 때

**무엇을 하나요?**
- 용어 통일성을 체크합니다
- 기능 중복을 제거합니다
- 고객 가치 일관성을 확보합니다
- 공통 모듈과 정책을 추출합니다

**사용 예시:**
```bash
/appkit.merge
/appkit.merge "API 통합 중점"
```

**생성되는 파일:**
- `docs/appkit/merge/concept-map.md` - 통합 컨셉 맵
- `docs/appkit/merge/terminology.md` - 표준 용어 사전
- `docs/appkit/merge/consolidated-specs.md` - 통합 명세

---

### 7️⃣ `/appkit.design` - 개발 준비

**언제 사용하나요?**
- 기획이 정돈된 후
- 개발팀에게 전달할 기술 스펙이 필요할 때

**무엇을 하나요?**
- ERD(Entity Relationship Diagram)를 설계합니다
- RESTful API 엔드포인트를 정의합니다
- 기술 정책(Rate Limiting, Error Handling 등)을 정리합니다
- 화면-API 매핑을 생성합니다

**사용 예시:**
```bash
/appkit.design
/appkit.design "persona 도메인 집중"
```

**생성되는 파일:**
- `docs/appkit/design/entities.md` - 데이터 모델
- `docs/appkit/design/apis.md` - API 설계
- `docs/appkit/design/tech-policies.md` - 기술 정책
- `docs/appkit/design/screen-api-map.md` - 화면 매핑

---

## 🚀 빠른 시작 가이드

### 1단계: 아이디어 입력
```bash
/appkit.new 내 서비스 아이디어를 간단히 설명
```

Claude가 분석하고 서비스 컨셉을 제시합니다. 확인 후 "Good" 또는 "진행"이라고 입력하면 파일이 생성됩니다.

### 2단계: 기능 구체화
```bash
/appkit.spec 001-기능명 "구체적인 시나리오나 요구사항"
```

여러 번 실행하며 각 기능을 점진적으로 상세화합니다.

### 3-7단계: 순차 진행
```bash
/appkit.customer  # 고객 정의
/appkit.sales     # 세일즈 메시지
/appkit.mvp       # MVP 범위
/appkit.merge     # 기획 정돈
/appkit.design    # 개발 준비
```

## 💡 사용 팁

### ✅ Do (이렇게 하세요)

1. **순서대로 진행하기**: 각 단계는 이전 단계의 결과물을 활용합니다
2. **구체적으로 입력하기**: "검색 기능"보다 "위치 기반으로 5km 내 코트 검색, 거리순 정렬"
3. **여러 번 실행하기**: 특히 `/appkit.spec`은 여러 번 실행하며 디테일을 추가합니다
4. **자연어로 편하게**: "퇴근길 지하철에서 예약하는 시나리오" 같은 자연스러운 표현 사용

### ❌ Don't (이런 건 피하세요)

1. **단계 건너뛰기**: 각 단계는 논리적으로 연결되어 있습니다
2. **한 번에 완벽하게 하려는 욕심**: 점진적으로 개선하는 것이 더 효과적입니다
3. **기술 용어로만 설명**: 고객 관점의 자연어가 더 좋은 결과를 만듭니다

## 📂 생성되는 파일 구조

```
docs/appkit/
├── overview.md                    # 서비스 개요 (from /appkit.new)
├── specs/                         # 기능 명세들
│   ├── 001-xxx/spec.md           # (from /appkit.spec)
│   ├── 002-yyy/spec.md
│   └── ...
├── customer-persona.md            # 타겟 고객 (from /appkit.customer)
├── customer-journey.md            # 고객 여정
├── sales-landing.md               # 랜딩 페이지 (from /appkit.sales)
├── value-proposition.md           # 가치 제안
├── mvp-scope.md                   # MVP 범위 (from /appkit.mvp)
├── mvp-metrics.md                 # 검증 지표
├── merge/                         # 통합 문서 (from /appkit.merge)
│   ├── concept-map.md
│   ├── terminology.md
│   └── consolidated-specs.md
└── design/                        # 개발 준비 (from /appkit.design)
    ├── entities.md
    ├── apis.md
    ├── tech-policies.md
    └── screen-api-map.md
```

## 🎓 예시 프로젝트

### 테니스 코트 예약 앱 기획하기

```bash
# 1. 아이디어 스케치
/appkit.new 테니스 코트 실시간 예약 앱. 위치 기반 검색과 자동 할인 기능

# 2. 기능 구체화
/appkit.spec 001-search "현재 위치 5km 내 코트 검색, 실시간 예약 가능 여부 표시"
/appkit.spec 002-booking "3초 예약 프로세스: 날짜 선택 → 시간 선택 → 결제"
/appkit.spec 002-booking "타임딜: 예약 2일 전 30% 자동 할인"

# 3. 고객 정의
/appkit.customer

# 4. 세일즈 메시지
/appkit.sales

# 5. MVP 범위
/appkit.mvp "2-week validation"

# 6. 기획 정돈
/appkit.merge

# 7. 개발 준비
/appkit.design
```

2-3시간이면 개발팀에게 전달할 수 있는 완전한 기획 문서가 완성됩니다.

## 🤝 AppKit의 철학

### "논리적 사고의 7단계"

AppKit은 PM/기획자의 사고 과정을 체계화한 것입니다:

1. **What** - 무엇을 만드나? (아이디어 스케치)
2. **How** - 어떻게 작동하나? (기능 구체화)
3. **Who** - 누가 쓰나? (고객 스토리)
4. **Why** - 왜 써야 하나? (세일즈 메시지)
5. **When** - 언제 만드나? (MVP 범위)
6. **Align** - 일관성 있나? (기획 정돈)
7. **Build** - 어떻게 구현하나? (개발 준비)

### "AI는 맥락을 놓친다. 사람이 통합하라."

각 단계에서 AI가 생성한 내용을 사람이 검토하고 통합하는 것이 중요합니다.
특히 `/appkit.merge` 단계에서는 AI가 생성한 여러 문서의 일관성을 사람이 확인합니다.

---

## 🔧 트러블슈팅

### Q: 파일이 생성되지 않아요
A: `/appkit.new`를 먼저 실행했는지 확인하세요. 다른 커맨드들은 `/appkit.new`가 생성한 구조를 기반으로 동작합니다.

### Q: spec 파일이 너무 길어져요
A: 괜찮습니다. `/appkit.spec`은 점진적으로 내용을 추가하도록 설계되었습니다. 나중에 `/appkit.merge`에서 정리됩니다.

### Q: 순서를 꼭 지켜야 하나요?
A: 권장사항입니다. 특정 단계만 필요하다면 건너뛸 수 있지만, 순서대로 하면 가장 체계적인 결과를 얻습니다.

### Q: 중간에 방향을 바꾸고 싶어요
A: `/appkit.new`를 다시 실행하거나, 해당 단계의 커맨드를 다시 실행하면 됩니다. 이전 내용은 보존됩니다.

---

## 📝 버전 정보

- **Version**: 1.0.0
- **Created**: 2025-11-19
- **Philosophy**: "Think like a PM, Execute like an Engineer"

---

## 🙋 도움이 필요하신가요?

각 커맨드 파일을 열어보면 더 상세한 설명이 있습니다:
- `.claude/commands/appkit.new.md`
- `.claude/commands/appkit.spec.md`
- `.claude/commands/appkit.customer.md`
- `.claude/commands/appkit.sales.md`
- `.claude/commands/appkit.mvp.md`
- `.claude/commands/appkit.merge.md`
- `.claude/commands/appkit.design.md`

궁금한 점이 있으면 Claude에게 물어보세요:
```
"/appkit.spec 커맨드를 어떻게 사용하나요?"
"MVP 범위를 어떻게 정하나요?"
```
