# Korean Video Captioning 발표 자료

> **프로젝트**: 대한민국 배경영상 한국어 캡셔닝  
> **목표**: Vision-Language Model을 활용한 한국어 비디오 캡셔닝 성능 최적화

---

## 발표 구성

### 1. 프로젝트 소개 ([01_project_intro.md](01_project_intro.md))

| 섹션 | 내용 | 슬라이드 수 (권장) |
|------|------|-------------------|
| 1.1 EDA 요약 | 데이터셋 통계, 카테고리 분포, 캡션 분석 | 2-3장 |
| 1.2 리소스 설정 및 근거 | GPU/모델/하이퍼파라미터 선택 이유 | 2장 |
| 1.3 프로젝트 목표 | METEOR, SigLIP, Diversity 지표 | 2장 |

### 2. 모델 학습 ([02_model_training.md](02_model_training.md))

| 섹션 | 내용 | 슬라이드 수 (권장) |
|------|------|-------------------|
| 2.1 모델 아키텍처 | VLM 구조, Projector 4종 비교 | 2-3장 |
| 2.2 학습 전략 | 2-Stage Training, LoRA 설정 | 1-2장 |
| 2.3 적용된 최적화 | 품질 개선 / 학습 시간 단축 | 2장 |
| 2.4 실험 결과 | E5-v2, E5-v3 결과, Mode Collapse | 2-3장 |

### 3. 추후 개선방향 ([03_future_improvements.md](03_future_improvements.md))

| 섹션 | 내용 | 슬라이드 수 (권장) |
|------|------|-------------------|
| 3.1 선택지별 분석 | 5가지 옵션 장단점 | 2-3장 |
| 3.2 권장 로드맵 | Phase 1~3 계획 | 1장 |
| 3.3 핵심 교훈 | 3가지 핵심 인사이트 | 1장 |

---

## 핵심 메시지

### 문제 정의
- 기존 VLM은 영어 중심 → 한국어 캡셔닝 성능 제한
- 베이스라인 METEOR: 0.3052

### 접근 방식
- Qwen3-8B (한국어 토큰 효율 2.3배) + CLIP Vision Encoder
- 4종 Projector 비교 (Linear, MLP, C-Abstractor, Perceiver)
- SigLIP2 기반 Vision-Language 정렬 평가

### 주요 발견
- **C-Abstractor (206M) Mode Collapse 발생** → 작은 데이터셋에서 큰 모델 위험
- **SigLIP 단독 평가 한계** → Diversity 지표 필수

### 다음 단계
- 단순 Projector (Linear 4M, MLP 8M) 검증
- Full Dataset 학습 후 METEOR 0.40+ 목표

---

## 파일 구조

```
presentation/
├── README.md                    # 본 파일 (발표 개요)
├── 01_project_intro.md          # 1. 프로젝트 소개
├── 02_model_training.md         # 2. 모델 학습
├── 03_future_improvements.md    # 3. 추후 개선방향
└── assets/                      # 이미지 참조 경로
```

---

## 참조 문서

| 카테고리 | 파일 경로 |
|----------|----------|
| **EDA** | `local_train/eda/reports/00_summary.md` |
| **EDA 그래프** | `local_train/eda/figures/` |
| **데이터셋** | `korean_video_captioning/docs/01_DATASET.md` |
| **모델 아키텍처** | `korean_video_captioning/docs/02_MODEL_ARCHITECTURE.md` |
| **학습 전략** | `korean_video_captioning/docs/03_TRAINING_STRATEGY.md` |
| **평가 지표** | `korean_video_captioning/docs/05_EVALUATION_METRICS.md` |
| **SigLIP Study** | `korean_video_captioning/siglip_study/reports/` |

---

## 발표 시간 배분 (예시: 15분)

| 파트 | 시간 | 내용 |
|------|------|------|
| 1. 프로젝트 소개 | 4분 | EDA, 리소스, 목표 |
| 2. 모델 학습 | 7분 | 아키텍처, 학습, 최적화, 결과 |
| 3. 추후 개선방향 | 3분 | 옵션, 로드맵, 교훈 |
| Q&A | 1분 | 질의응답 |

---

*Last Updated: 2026-01-21*
# korean_video_captioning_html
# korean_video_captioning_html
