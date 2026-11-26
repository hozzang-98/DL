# DL

딥러닝 강의 실습 노트 모음. 강의 자료를 따라가며 작성한 노트북이라 모델별로 코드 수준은 고르지 않고, 데이터는 노트북 안에서 내려받거나 Colab 드라이브 경로를 참조한다. 대부분 TensorFlow/Keras 기반이며 일부는 PyTorch.

## 노트북 목록

| 주제 | 노트북 | 데이터 | 내용 |
| --- | --- | --- | --- |
| MLP | `BostonHousing_Regression(mlp).ipynb` | Keras boston_housing | Dense 64-32-1 회귀, 표준화 |
| MLP | `Fashion_MNIST(mlp).ipynb` | Fashion-MNIST | Dense 512-10 분류, 모델 저장/복원/재학습 |
| CNN | `Convolutional Neural Network.ipynb` | Fashion-MNIST | Conv2D 기본 CNN |
| CNN | `CIFAR-10_Classification(cnn).ipynb` | CIFAR 10클래스 부분집합 (5,000/1,000) | Conv2D 3층 CNN |
| CNN | `Fashion_MNIST(torch).ipynb` | MNIST (`fetch_openml('mnist_784')`) | PyTorch Conv2D 2층 CNN (이름과 달리 MNIST) |
| CNN | `Regularizers.ipynb` | MNIST, iris | BatchNormalization/Dropout CNN, EarlyStopping |
| 이미지 로더/증강 | `ImageDataGenerator.ipynb` | cats_and_dogs_filtered | `flow_from_directory`, DirectoryIterator 속성 |
| 이미지 로더/증강 | `Image_Augmentation.ipynb` | 단일 이미지 | flip/shift 등 증강 결과 확인 |
| 전이학습 | `RCP_Classification(cnn).ipynb` | 가위바위보 (rps) | 직접 설계한 CNN |
| 전이학습 | `RCP_Classification(TransferLearning).ipynb` | 가위바위보 (rps) | VGG16 backbone 동결 + Dense 분류기 |
| 전이학습 | `VGG.ipynb` | ImageNet 사전학습, 드라이브 이미지 20장 | VGG16 추론, 2클래스 전이학습 |
| 객체 탐지 | `Yolo.ipynb` | 드라이브 내 tl_dataset | yolo-v4-tf.keras 로 10 epoch 학습 |
| RNN | `weather_prediction(rnn).ipynb` | Jena climate (온도 단변량) | 20스텝 관측 → 다음 값, SimpleRNN(8) |
| PyTorch 기초 | `Pytorch_Earlystopping.ipynb` | 임의 데이터, iris | Dataset/DataLoader, early stopping 수동 구현 |
| ML (비딥러닝) | `House_regression.ipynb` | Kaggle House Prices | Lasso/ElasticNet/KernelRidge/SVR/RF/XGB + Stacking |
| ML (비딥러닝) | `S&P_Investing(knn).ipynb` | yfinance SPY 2012~2021 | Open-Close, High-Low 피처로 KNN 등락 예측 (test acc 0.517) |
| RAG | `RAG_with_Ko_PlatYi_6B.ipynb` | PDF 1건 | 4bit 양자화 LLM(`NCSOFT/Llama-VARCO-8B-Instruct`, 파일명과 다름) + LangChain + FAISS |
| RAG | `ColPali-Vision-based-RAG.ipynb` | PDF 2건 | byaldi `colpali-v1.2` 페이지 이미지 검색 → gpt-4o 답변, Chroma 텍스트 RAG 비교 |

## 참고

- 대부분 Colab 에서 실행했으며 `/content/...`, `/content/drive/...` 경로는 환경에 맞게 바꿔야 한다.
- 평가 결과 수치는 노트북 출력에 남아 있는 것만 유효하다. 여러 노트북은 `evaluate` 출력이 저장되지 않았다.
- RAG 노트북은 HF 토큰, OpenAI 키를 Colab userdata 로 읽는다. 코드에 하드코딩된 키는 없다.
