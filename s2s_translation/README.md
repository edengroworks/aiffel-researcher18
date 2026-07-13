# Seq2seq으로 번역기 만들기

AIFFEL DeepDive(NLP) 프로젝트 — GRU Encoder-Decoder에 **Bahdanau Attention**을 더한 번역기를 PyTorch로 직접 구현했습니다.

## 내용

| 단계 | 내용 |
|---|---|
| 1. 준비 | 프로젝트 디렉토리, matplotlib 한글 폰트 설정 |
| 2. 데이터 전처리 | 영어-스페인어 말뭉치 3만 쌍 · 정규식 정제 · SentencePiece 토큰화 · 패딩 직접 구현 |
| 3. 모델 설계 | `BahdanauAttention` / `Encoder` / `Decoder` / `Seq2SeqAttention` |
| 4. 훈련 | Adam + CrossEntropyLoss(PAD mask) · Teacher Forcing · train/eval step · Attention Map 시각화 |
| 5. 프로젝트 | **한국어 → 영어 번역기** — 한영 병렬 말뭉치 정제(중복 제거, 길이 필터) · mecab 형태소 토큰화 · vocab 10,000 |

## 환경

- Mac 로컬 (Apple Silicon `mps`) / Python 3.11 / PyTorch
- 원본 강의는 아이펠 클라우드(cuda) 기준이며, 경로·장치·폰트를 로컬용으로 수정했습니다
- 데이터는 노트북 실행 시 자동 다운로드됩니다 (spa-eng, korean-english-park)
