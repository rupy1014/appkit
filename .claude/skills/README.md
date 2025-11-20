# AI_잡돌이 Skills Overview

이 디렉토리는 프로젝트 전용 AI 스킬들을 포함합니다. 각 스킬은 특정 콘텐츠 제작 작업에 최적화되어 있습니다.

## 📚 Available Skills

### 1️⃣ YouTube Narration Coach
**디렉토리**: `youtube-narration-coach/`
**목적**: 유튜브 나레이션 대본 분석 및 개선

**주요 기능**:
- 7단계 프레임워크 기반 분석 (HOOK→PROBLEM→AGITATE→SOLUTION→VALUE→PROOF→CTA)
- 한국 시청자 심리 트리거 체크
- 섹션별 체크리스트 제공
- 구체화 질문을 통한 코칭 방식
- 완주율 최적화 피드백

**사용 방법**:
```
"이 대본 분석해줘"
"유튜브 스크립트 피드백 필요해"
"프레임워크 적용해서 봐줘"
```

---

### 2️⃣ Landing Page Copywriter
**디렉토리**: `landing-page-copywriter/`
**목적**: 고전환율 랜딩페이지 카피 생성

**주요 기능**:
- PAS/AIDA/StoryBrand 프레임워크 적용
- Hero, Problem, Solution, CTA 섹션 생성
- A/B 테스트 제안
- 전환 최적화 팁
- 사회적 증거 구조화

**사용 방법**:
```
"이 제품으로 랜딩페이지 카피 써줘"
"PAS 프레임워크로 세일즈 페이지 만들어줘"
"CTA 최적화해줘"
```

---

### 3️⃣ PPT Slide Extractor ✨
**디렉토리**: `ppt-slide-extractor/`
**목적**: 유튜브 나레이션 대본에서 영상 송출용 PPT 장표 추출

**핵심 컨셉**:
- 유튜브 시청자가 나레이션과 함께 보는 시각 자료
- 복잡한 설명을 단순화해서 전달
- 오프라인 발표 자료 아님 (발표자 노트, 제스처 가이드 X)

**주요 기능**:
- 6가지 장표 타입 자동 분류 (Title/Problem/Process/Comparison/Data/CTA)
- 핵심 키워드 추출 (5개 이하)
- 이미지 제안 (간단히 1-2줄)
- 타임스탬프 연동

**핵심 원칙**:
- **1장 = 1메시지**: 한 슬라이드에 하나의 핵심만
- **3초 룰**: 시청자가 3초 안에 파악 가능
- **Less is More**: 텍스트 최소화, 키워드 중심
- **나레이션 보조**: 슬라이드는 말하는 내용의 시각적 보조

**장표 타입**:
1. **타이틀**: 영상 시작, 섹션 전환
2. **문제 제시**: 고통 포인트 시각화
3. **프로세스**: 단계별 워크플로우 (1→2→3→4)
4. **비교**: Before/After, A vs B
5. **데이터**: 숫자, 통계, 사회적 증거
6. **CTA**: 행동 유도 (3단계 깔때기)

**출력 구조** (심플):
```
SLIDE #N: [타입]
├─ ⏰ [0:00-0:15]
├─ 제목: [5-8단어]
├─ 내용: [키워드 3-5개]
└─ 이미지: [간단한 설명 1-2줄]
```

**사용 방법**:
```
"이 나레이션으로 PPT 만들어줘"
"대본에서 장표 뽑아줘"
"영상용 슬라이드 필요해"
"유튜브 PPT 추출해줘"
```

**예상 장표 수**:
- 10분 영상: 8-12장
- 15분 영상: 12-18장
- 평균: 1-1.5분당 1장

---

## 🎯 Skills Usage Workflow

### Workflow 1: 대본 작성 → 장표 추출
```
1. YouTube Narration Coach로 대본 작성/개선
   ↓
2. 프레임워크 기반 완성도 검증
   ↓
3. PPT Slide Extractor로 장표 자동 추출
   ↓
4. 디자이너에게 전달 or 직접 PPT 제작
```

### Workflow 2: 제품 → 랜딩페이지 → 발표 자료
```
1. Landing Page Copywriter로 제품 카피 작성
   ↓
2. YouTube Narration Coach로 발표 대본 변환
   ↓
3. PPT Slide Extractor로 피치덱 생성
```

---

## 📁 Directory Structure

```
.claude/skills/
├── README.md                       (이 파일)
├── youtube-narration-coach/
│   └── SKILL.md                    (스킬 정의)
├── landing-page-copywriter/
│   └── SKILL.md
└── ppt-slide-extractor/
    └── SKILL.md
```

---

## 🔧 How Skills Work

### Activation
스킬은 다음 상황에서 자동 활성화됩니다:
1. **키워드 감지**: 특정 단어/구문 감지 시
2. **파일 확장자**: `.md`, `.txt` 대본 파일 제공 시
3. **명시적 요청**: "~해줘" 형태의 직접 요청

### Coordination
여러 스킬이 동시에 필요한 경우, Claude가 자동으로 조율합니다:
- **순차 실행**: 대본 작성 → 분석 → 장표 추출
- **병렬 실행**: 랜딩페이지 카피 + PPT 슬라이드 동시 생성
- **반복 개선**: 피드백 → 수정 → 재추출

---

## 💡 Best Practices

### For YouTube Narration Coach
- 대본 초안 단계부터 활용
- 섹션별 순차 개선 (한 번에 다 고치기 X)
- 프레임워크 질문에 구체적으로 답변

### For Landing Page Copywriter
- 제품/서비스 정보 구체적으로 제공
- 타겟 청중 명확히 정의
- A/B 테스트 제안 적극 활용

### For PPT Slide Extractor
- 대본 완성도 70% 이상일 때 사용
- 장표 스타일 미리 선택 (미니멀/정보형/혼합)
- 추출 후 특정 슬라이드만 수정 가능
- 디자인 가이드라인을 디자이너에게 전달

---

## 🚀 Coming Soon

### Planned Skills
- **Video Script Analyzer**: 영상 편집 타임라인 생성
- **Thumbnail Copy Generator**: 썸네일 텍스트 추출
- **SEO Optimizer**: 제목/태그/설명 최적화
- **A/B Test Generator**: 다양한 버전 자동 생성

---

## 📞 Feedback

스킬 개선 제안이나 버그 리포트:
- 프로젝트 이슈 트래커 사용
- 또는 CLAUDE.md에 피드백 섹션 추가

---

**Last Updated**: 2025-11-08
**Total Skills**: 3
**Latest Addition**: PPT Slide Extractor v1.0
