# appkit.merge

**기획 정돈 - 흩어진 기획 문서를 일관되게 통합**

---

## Quick Reference
- **Workflow**: Step 6/7 (기획 정돈)
- **Token Budget**: ~5,000 tokens
- **Parallel Operations**: YES (read all source files)
- **User Interaction**: NO (automatic analysis & consolidation)
- **Progressive Loading**: YES (headers and key sections only)

## Overview

**This is Step 6 of the logical thinking 7-step workflow**:

```
논리적 사고 7단계:
1. /appkit.new      → 아이디어 스케치 (어떤 서비스인지?)
2. /appkit.spec     → 기능 구체화 (뭐가 필요할까? 누가 쓸까?)
3. /appkit.customer → 고객 스토리 (고객의 하루, 고민, 해결)
4. /appkit.sales    → 세일즈 랜딩 구성 (어떻게 설득할까?)
5. /appkit.mvp      → MVP 범위 정하기 (최소한으로 검증하려면?)
6. /appkit.merge    → 기획 정돈 (흩어진 기획 통합) ← YOU ARE HERE
7. /appkit.design   → 개발 준비 (API, ERD, 기술 스펙)
```

## Purpose

MVP 범위가 정해지면, 이제 지금까지 만든 기획 문서들을 정리할 차례입니다.
spec, customer, mvp를 각각 만들다 보면 AI가 맥락을 놓치고 일관성 없이 생성합니다.
**기획 레벨**에서 흩어진 내용을 통합하고, 중복과 충돌을 해소합니다.

**핵심 질문**: "기획이 일관적인가? 중복은? 용어가 통일됐나?"

---

## When to Use

- `/appkit.mvp`로 MVP 범위를 정한 후 (Step 5 완료 후)
- spec, customer, mvp 결과물이 준비되었을 때
- 기획 문서 간 중복이나 충돌이 보일 때
- 용어와 컨셉을 통일해야 할 때
- 개발 준비(design) 전 기획을 정돈하고 싶을 때

---

## Usage

```bash
/appkit.merge
/appkit.merge "특히 spec과 customer 용어 통일"
/appkit.merge "MVP 범위 기반으로 우선순위 재조정"
```

---

## What I'll Do

### 1. 소스 문서 수집 (Parallel Loading)

**⚡ CRITICAL - PARALLEL EXECUTION REQUIRED**:
Read ALL source files in a SINGLE message with multiple Read/Glob tool calls.

**Performance Impact**:
- ❌ Sequential: 5 files × 2 seconds = 10 seconds
- ✅ Parallel: 1 message with 5 Read calls = 2 seconds
- **5x speed improvement**

**Execution Pattern**:
Use ONE message with multiple tool calls:
- Glob pattern for all spec files: `docs/appkit/specs/*/spec.md`
- Read customer-persona.md
- Read customer-journey.md
- Read mvp-scope.md
- Read mvp-metrics.md

**Progressive Loading Strategy**:
Load ONLY necessary sections from each file:
```markdown
From spec files:
- Feature Name (first 10 lines)
- User Value section only
- Dependencies section only
(Skip: detailed journey, business rules, edge cases)

From customer files:
- Primary Persona only (first 50 lines)
- Pain Points section
(Skip: secondary personas, full journey details)

From MVP files:
- Phase 0 features list only
- Success metrics section
(Skip: detailed phase descriptions, examples)
```

**Token Savings**:
- ❌ Full files: 10 specs × 500 lines = 5,000 lines
- ✅ Progressive: 10 specs × 50 lines = 500 lines
- **90% token reduction**

**읽을 파일들**:
- `docs/appkit/specs/*/spec.md` (모든 기능 스펙 - 핵심 섹션만)
- `docs/appkit/customer-persona.md` (타겟 고객 - Primary만)
- `docs/appkit/customer-journey.md` (고객 여정 - Pain Points만)
- `docs/appkit/mvp-scope.md` (MVP 범위 - Phase 0만)
- `docs/appkit/mvp-metrics.md` (검증 지표 - Success Metrics만)

### 2. 기획 일관성 분석

**분석 항목**:

#### A. 용어 통일성
```markdown
## 용어 충돌 발견

❌ **Spec에서**: "페르소나 설정"
❌ **Customer에서**: "캐릭터 프로필"
❌ **MVP에서**: "인물 정보"

✅ **통일 제안**:
→ 표준 용어: "페르소나"
→ 모든 문서에 일관되게 적용
```

#### B. 기능 중복 확인
```markdown
## 중복 기능 발견

❌ **001-persona/spec.md**:
- 이미지 생성 기능 언급

❌ **002-content/spec.md**:
- 이미지 생성 기능 중복 설명

✅ **통합 제안**:
→ 002-content에서 통합 관리
→ 001-persona는 002-content 참조
```

#### C. 고객 가치 일관성
```markdown
## 가치 제안 충돌

❌ **Spec**: "100명 자동 관리"
❌ **Customer**: "15시간 → 1시간 시간 절약"
❌ **Sales**: "월 1억 수익"

✅ **핵심 가치 통일**:
→ Primary Value: "시간 절약 (15시간 → 1시간)"
→ Secondary Value: "확장성 (100명 관리)"
→ Ultimate Goal: "월 1억 수익 달성"
```

### 3. MVP 범위 기반 우선순위 조정
```markdown
## MVP 범위 재확인

**Phase 0 (MVP - 2주)**:
✅ 페르소나 관리 (001-persona)
✅ 콘텐츠 자동 생성 (002-content)
✅ 스케줄링 (003-schedule)
❌ 성과 분석 (004-analytics) → Phase 1로 이동
❌ 수익화 관리 (005-monetize) → Phase 2로 이동

**우선순위 조정**:
1. **Must Have** (없으면 MVP 불가):
   - 001-persona, 002-content, 003-schedule

2. **Should Have** (있으면 좋음):
   - 004-analytics (Phase 1)

3. **Nice to Have** (나중에):
   - 005-monetize (Phase 2)

→ Spec 문서에서 Phase 0 외 기능은 "Future" 섹션으로 이동
```

### 4. 컨셉 맵 생성

**Output**: `docs/appkit/merge/concept-map.md`

```markdown
# Concept Map (통합 컨셉 맵)

*생성 기준: spec, customer, mvp 통합*
*생성일: 2025-11-20*

---

## 핵심 컨셉 정의

### 서비스 컨셉
"AI 인플루언서 100명을 자동으로 운영하는 시스템"

### 핵심 가치 (통일)
1. **Primary**: 시간 절약 (15시간 → 1시간)
2. **Secondary**: 확장성 (100명 자동 관리)
3. **Ultimate Goal**: 월 1억 수익

### 타겟 사용자
- **Primary**: 본인 (AI 인플루언서 운영자)
- **Pain Point**: 수동 작업 불가능
- **Goal**: 완전 자동화

---

## 기능 통합 맵

### Phase 0 (MVP - 2주)

**001-persona** (페르소나 관리)
- 정의: 캐릭터별 성격, 톤앤매너 설정
- 입력: 캐릭터 정보 (이름, 나이, 성격)
- 출력: 페르소나 DB 저장
- 의존성: 없음

**002-content** (콘텐츠 자동 생성)
- 정의: 페르소나 기반 이미지 + 캡션 자동 생성
- 입력: 페르소나 ID, 주제
- 출력: 이미지 (Midjourney), 캡션 (GPT)
- 의존성: 001-persona (필수)

**003-schedule** (스케줄링)
- 정의: 매일 아침 7시 자동 생성 실행
- 입력: 스케줄 설정
- 출력: Cron job 실행
- 의존성: 002-content (필수)

---

## 용어 사전 (통일된 표현)

| 개념 | 표준 용어 | 금지 용어 |
|------|-----------|-----------|
| 캐릭터 정보 | 페르소나 | 캐릭터 프로필, 인물 정보 |
| 자동 생성 | 콘텐츠 생성 | 포스트 제작, 글쓰기 |
| 예약 실행 | 스케줄링 | 타이머, 자동 실행 |
| 성과 추적 | 분석 | 통계, 모니터링 |

---

## 데이터 흐름

```
[페르소나 DB] → [콘텐츠 생성] → [Instagram API]
       ↑              ↑                ↑
   001-persona   002-content    003-schedule
```

**데이터 엔티티** (기획 레벨):
1. Persona (페르소나 정보)
2. Content (생성된 콘텐츠)
3. Schedule (스케줄 설정)
4. Post (포스팅 기록)

*상세 데이터 모델은 /appkit.design에서 생성*
```

### 5. 고객 여정과 기능 매핑

**Output**: `docs/appkit/merge/journey-feature-map.md`

```markdown
# 고객 여정 - 기능 매핑

*Customer Journey → Feature Mapping*

---

## 현재 상황 (Before)

**새벽 6시**: "100개 콘텐츠 어떻게 만들지..." (막막)
→ **해결 기능**: 없음 (수동 작업)

**오전 9시**: 20개째 이미지 생성 중 (지침)
→ **해결 기능**: 002-content (자동 생성)

**오후 3시**: 50개째 캡션 작성 중 (번아웃)
→ **해결 기능**: 002-content (자동 생성)

**저녁 9시**: 결국 20개 못 올림 (좌절)
→ **해결 기능**: 003-schedule (자동 포스팅)

---

## 미래 상황 (After - MVP 적용)

**전날 밤 11시**: 내일 주제만 설정 (5분)
→ **사용 기능**: 001-persona (주제 입력)

**아침 7시**: 시스템이 100개 자동 생성 (무인)
→ **사용 기능**: 003-schedule → 002-content

**아침 8시**: 커피 마시며 퀄리티 체크 (30분)
→ **사용 기능**: 004-analytics (Phase 1)

---

## 기능별 고객 가치

**001-persona**:
- Pain 해소: "매번 캐릭터 설정 반복" → "한번 설정, 계속 사용"
- 시간 절약: 10분/캐릭터 → 1분 (첫 설정)

**002-content**:
- Pain 해소: "100개 수동 생성 불가능" → "100개 자동 생성"
- 시간 절약: 10시간 → 0시간

**003-schedule**:
- Pain 해소: "아침마다 실행 필요" → "자동 실행"
- 시간 절약: 5분/일 → 0분
```

### 6. 통합 후 구조 재정의

**Before (분산)**:
```
docs/appkit/
├── specs/
│   ├── 001-persona/spec.md (용어 불일치)
│   ├── 002-content/spec.md (중복 설명)
│   └── 003-schedule/spec.md
├── customer-persona.md (용어 다름)
├── customer-journey.md
├── mvp-scope.md (우선순위 모호)
└── mvp-metrics.md
```

**After (통합)**:
```
docs/appkit/merge/
├── concept-map.md              # 핵심: 통합 컨셉 맵
├── journey-feature-map.md      # 고객 여정 - 기능 매핑
├── terminology.md              # 표준 용어 사전
├── consolidated-specs.md       # 통합된 기능 명세
└── mvp-priority.md             # 재조정된 우선순위
```

**구조 설명**:
- `concept-map.md`: 모든 문서의 컨셉을 하나로 통합
- `journey-feature-map.md`: 고객 여정과 기능 매핑
- `terminology.md`: 통일된 용어 사전
- `consolidated-specs.md`: 중복 제거된 기능 명세
- `mvp-priority.md`: MVP 기반 우선순위

### 7. 충돌 해결

**충돌 패턴 식별**:

```markdown
## Conflicts Detected

⚠️ **Conflict #1**: 이미지 생성 해상도
- 001-persona: 512x512
- 002-content: 1080x1080
→ **해결**: content-safety.md에 용도별 최소 해상도 정의

⚠️ **Conflict #2**: API 호출 우선순위
- 001: persona 우선
- 002: content 우선
→ **해결**: rate-limiter.md에 우선순위 큐 정의

⚠️ **Conflict #3**: 에러 시 재시도 횟수
- 001: 5회
- 002: 3회
→ **해결**: error-handling.md에 통일 (3회)
```

---

## Output Files

### 생성될 파일 구조:

```
docs/appkit/merge/
├── specs/               (통합된 개별 기능)
│   ├── 001-persona/
│   ├── 002-content/
│   ├── 003-schedule/
│   └── 004-posting/
├── common/              (공통 모듈 & 정책)
│   ├── 001-image-generation/
│   ├── 002-rate-limiter/
│   ├── 003-error-handler/
│   ├── 004-content-safety/
│   ├── 005-api-limits/
│   └── 006-data-management/
├── overview.md          (전체 통합 요약)
└── dependencies.md      (의존성 그래프)
```

### 파일별 상세:

1. **`merge/specs/00X-*/spec.md`**
   - 원본 specs에서 중복 제거
   - common 모듈 참조 추가
   - 의존성 명시

2. **`merge/common/001-image-generation/module.md`**
   - Midjourney API 통합 로직
   - 이미지 생성 공통 인터페이스
   - 사용 예시

3. **`merge/common/002-rate-limiter/module.md`**
   - API별 제한 정책
   - 우선순위 큐 시스템
   - 재시도 로직

4. **`merge/common/003-error-handler/module.md`**
   - 통일된 에러 처리
   - 로깅 정책
   - 알림 규칙

5. **`merge/common/004-content-safety/policy.md`**
   - 브랜드 안전성 필터
   - 콘텐츠 검증 규칙
   - 언어/문화 가이드

6. **`merge/common/005-api-limits/policy.md`**
   - Midjourney: 시간당 50회
   - OpenAI: 분당 60회
   - Instagram: 일 200개

7. **`merge/common/006-data-management/policy.md`**
   - 저장 위치 및 구조
   - 보존 기간
   - 백업 정책

8. **`merge/overview.md`**
   - 중복 제거 요약
   - 통합된 기능 목록
   - common 모듈 목록

9. **`merge/dependencies.md`**
   - 기능 간 의존성 그래프
   - 실행 순서
   - 순환 의존성 체크

---

## Integration Points

### 다른 명령어와의 연계:

- **From `/appkit.mvp`**: MVP Phase 0에 포함될 기능들
- **From `/appkit.spec`**: 각 기능별 스펙 파일
- **To 개발팀**: 정리된 스펙과 공통 모듈로 구현 시작

---

## Examples

### Example 1: 기본 통합

```bash
$ /appkit.merge

🔄 Spec Consolidation Analysis

**중복 기능 발견**: 2개
✅ image-generation 모듈로 통합

**공통 정책 추출**: 6개
✅ 001-image-generation (모듈)
✅ 002-rate-limiter (모듈)
✅ 003-error-handler (모듈)
✅ 004-content-safety (정책)
✅ 005-api-limits (정책)
✅ 006-data-management (정책)

**의존성 정리**: ✅ 순환 없음

**충돌 해결**: 3개
✅ 이미지 해상도 통일
✅ API 우선순위 정의
✅ 재시도 횟수 통일

✅ Created docs/appkit/merge/
✅ Generated merge/specs/ (4개)
✅ Generated merge/common/ (6개)
✅ Generated merge/overview.md
✅ Generated merge/dependencies.md
```

### Example 2: 특정 영역 집중

```bash
$ /appkit.merge "API 통합 중점"

🔄 API Integration Focus

**API 통합 분석**:
- Midjourney: 2곳에서 호출 → 통합
- OpenAI: 3곳에서 호출 → 통합
- Instagram: 1곳 (통합 불필요)

**Rate Limiting 정책**:
✅ common/005-api-limits/policy.md 생성
- Midjourney: 시간당 50회
- OpenAI: 분당 60회
- 우선순위 큐 필요

✅ Generated merge/common/001-image-generation/
✅ Generated merge/common/002-rate-limiter/
✅ Updated merge/specs/ (중복 제거)
```

---

## Key Principles

### Merge 원칙:

1. **DRY (Don't Repeat Yourself)**: 중복 코드/정책 제거
2. **Single Source of Truth**: 하나의 정의, 여러 참조
3. **Explicit Dependencies**: 암묵적 의존성 명시화
4. **Policy Centralization**: 정책은 한 곳에서 관리
5. **Conflict Resolution**: 충돌은 즉시 해결

---

## Tips

### 효과적인 통합을 위해:

1. **작은 단위로 시작**: 2-3개 기능부터 통합
2. **정책 우선**: 공통 규칙부터 정리
3. **의존성 체크**: 순환 의존성 방지
4. **문서화**: 통합 이유와 결정사항 기록
5. **점진적 리팩토링**: 한번에 다 바꾸지 말기

---

## Next Steps

### 이 명령어 실행 후:

**📍 다음 단계: Step 7 - `/appkit.design`** (개발 준비)
- 기획이 정돈되었으니 이제 개발 준비 단계로
- ERD, API 엔드포인트 설계
- 기술 정책 정의
- 개발팀에게 전달할 최종 기술 스펙 완성

---

## Version

- **Version**: 1.0.0
- **Created**: 2025-01-20
- **Philosophy**: "AI는 맥락을 놓친다. 사람이 통합하라."
