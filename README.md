# Graduate Admission Predictor

TensorFlow를 활용하여 대학원 합격 여부를 예측하는 딥러닝 모델을 구현한 프로젝트입니다.

이론으로 학습한 딥러닝의 동작 과정을 직접 코드로 구현하며 **데이터 전처리부터 모델 학습과 예측까지의 전체 흐름을 이해하기 위해 제작했습니다.**

## Tech Stack

- Python (3.12.6)
- TensorFlow / Keras
- NumPy
- Pandas


## 주요 기능

- CSV 데이터 로드 및 결측치 처리
- GRE 점수, GPA, 학부 순위를 활용한 합격 여부 예측
- 딥러닝 모델 학습 및 합격 확률 예측

## 학습 내용

- 데이터 전처리 및 특성(Feature)과 라벨(Label) 분리
- Sequential모델( 신경망을 연결한 하나의 모델) 과 Dense레이어 (앞쪽 레이어의 출력을 받아 계산하는 완전 연결 신경망 레이어) 를 활용한 신경망 구성
- ReLU 및 Sigmoid 활성화 함수
- Adam 옵티마이저와 Binary Crossentropy 손실 함수
- 모델 학습 및 예측

## 사용 방법

1. 리파지토리 clone 후 가상환경을 실행합니다.
2. 필요한 라이브러리를 설치합니다.

   ```bash
   pip install -r requirements.txt
   ```

3. `Dataset.csv`를 Python 파일과 같은 프로젝트 폴더에 준비합니다.
4. 예측 코드에서 원하는 입력값을 수정합니다.

   ```python
   predict = model.predict(np.array([
       [750, 3.70, 3],
       [400, 2.2, 1]
   ]))

   print(np.round(predict * 100))
   ```

   각 행의 입력값은 다음 순서로 구성됩니다.

   | 입력값 | 의미 | 예시 |
   |---|---|---|
   | 1번째 값 | GRE 점수 | `750` |
   | 2번째 값 | GPA | `3.70` |
   | 3번째 값 | 학부 순위(Rank) | `3` |

   원하는 GRE 점수, GPA, 학부 순위로 숫자를 변경한 뒤 코드를 실행하면 예측 결과를 확인할 수 있습니다.

   `predict * 100`은 모델이 반환한 값을 백분율로 환산하며, `np.round()`는 소수점을 반올림합니다.

5. Python 파일을 실행합니다.

   ```bash
   python main.py
   ```