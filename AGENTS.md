# AGENTS.md

NLP를 위한 핸즈온 머신러닝·딥러닝(PyTorch) 실습 저장소. 범용 코딩 에이전트를 위한 안내 문서.

## 명령어

- 설치: `pip install torch torchvision numpy pandas matplotlib visdom jupyter`
- 실행(.ipynb): Jupyter 또는 VS Code에서 셀 실행
- 실행(.py): `python <파일>.py` (노트북을 스크립트로 내보낸 버전)
- Docker: `pytorch/docker/`의 Dockerfile 참고
- 테스트: 별도 프레임워크 없음. GPU(CUDA) 없으면 CPU로 실행(느림)

## 구조

모든 자료는 `pytorch/` 아래에 있다.

- `pytorch/` — 강의 순서 평면 노트북(`01_`~`11_`) + 모델 스크립트(`resnet.py`, `vgg.py`) + 데이터 CSV
- `pytorch/CNN/` — CNN 실습(`.ipynb`+`.py` 쌍)
- `pytorch/RNN/` — RNN 실습(`.ipynb`+`.py`), `refactored/`, 자체 CSV 포함
- `pytorch/docker/` — CUDA/CPU Dockerfile

## 컨벤션

- 파일명은 강의 번호 접두어 사용, 하이픈/언더스코어 혼용은 기존 방식 유지
- 대부분 `.py`는 동명 `.ipynb`의 스크립트 버전 — 한쪽 수정 시 짝도 맞출 것
- 작업 중 파일은 `(wip)` 표기

## 주의

- 노트북은 데이터 CSV를 상대경로로 읽음. 루트 노트북은 `pytorch/data-*.csv`, RNN 노트북은 `pytorch/RNN/data-*.csv` 참조 → 노트북 이동 시 경로 깨짐
- `data-02-stock_daily.csv`가 `pytorch/`와 `pytorch/RNN/`에 각각 존재. 중복 삭제 금지(폴더별 참조)
- CSV 등 대용량 데이터 삭제 금지
- 파일명 NFC 통일, `.ipynb_checkpoints/`·`__pycache__/`·`.DS_Store` 커밋 금지
- CLAUDE.md와 내용 동일하게 유지
