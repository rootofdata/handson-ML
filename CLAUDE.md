# 프로젝트

자연어 처리(NLP)를 위한 핸즈온 머신러닝·딥러닝 실습 저장소. PyTorch 기반.

## 환경·실행

- 언어: Python 3, PyTorch
- 주요 패키지: `torch`, `torchvision`, `numpy`, `pandas`, `matplotlib`, `visdom`(일부 시각화 예제)
- 실행(.ipynb): Jupyter 또는 VS Code에서 셀 실행
- 실행(.py): 노트북을 스크립트로 내보낸 버전 (`python <파일>.py`)
- GPU: CUDA 사용 예제 있음. 없으면 CPU로도 동작하나 학습이 느림
- Docker 환경: `pytorch/docker/`의 Dockerfile 참고
- 실습 데이터(CSV): `pytorch/`(`data-01-test-score.csv` 등)와 `pytorch/RNN/`에 위치

## 폴더 구조

모든 자료는 `pytorch/` 아래에 있다.

- `pytorch/` — 강의 순서대로의 평면 노트북 (`01_`~`11_`: 텐서·회귀·분류·MNIST·CNN·RNN 등) + 모델 스크립트(`resnet.py`, `vgg.py`) + 데이터 CSV
- `pytorch/CNN/` — CNN 실습 (`.ipynb` + 동일 이름 `.py` 쌍)
- `pytorch/RNN/` — RNN 실습 (`.ipynb` + `.py`), `refactored/` 하위 포함, 자체 데이터 CSV 포함
- `pytorch/docker/` — CUDA/CPU용 Dockerfile

## 컨벤션

- 파일명: 강의 번호 접두어(`10_1_mnist_cnn`, `CNN_11-1-mnist_cnn`, `1-basics`) 사용. 하이픈/언더스코어 혼용은 기존 방식 유지
- 대부분의 `.py`는 같은 이름 `.ipynb`를 스크립트로 내보낸 것 — 한쪽을 고치면 짝도 함께 맞출 것
- 작업 중 상태 표기: `(wip)` 접두/접미 (예: `CNN_10-8-mnist_nn_selu(wip)`)

## 주의

- 노트북은 데이터 CSV를 상대경로로 읽는다. 루트 노트북은 `pytorch/data-*.csv`, RNN 노트북은 `pytorch/RNN/data-*.csv`를 참조하므로 노트북을 다른 폴더로 옮기면 경로가 깨진다
- 같은 `data-02-stock_daily.csv`가 `pytorch/`와 `pytorch/RNN/`에 각각 존재한다. 중복이라고 삭제하지 말 것 (각 노트북이 자기 폴더 기준으로 참조)
- CSV 등 대용량 데이터 파일 삭제 금지
- 한글은 거의 없지만 파일명은 NFC로 통일
- `.ipynb_checkpoints/`, `__pycache__/`, `.DS_Store` 커밋 금지
