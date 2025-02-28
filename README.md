Chest_Image_Segmentation
-----------------------
![image](https://github.com/user-attachments/assets/77806a3a-4b1b-451c-9239-b75bc4213ef2)

프로젝트 소개
---
U-Net 기법을 활용하여 COVID-19 관련 폐 질환의 이미지 세분화(Image Segmentation)를 구현한 코드이며, TensorFlow Dataset을 생성하여 의료 기반에 최적화된 U-Net 아키텍처 모델에 입력하도록 설계한 프로젝트

U-Net 아키텍처 및 특징
---
![image](https://github.com/user-attachments/assets/4cc0c451-058a-4f48-ac07-e99c2a80a88e)
●[1] Ronneberger, O., Fischer, P., & Brox, T. (2015). U-net: Convolutional networks for biomedical image segmentation. In Medical image computing and computer-assisted intervention–MICCAI 2015: 18th international conference, Munich, Germany, October 5-9, 2015, proceedings, part III 18 (pp. 234-241). Springer International Publishing.

프로젝트 전체 과정
---
![image](https://github.com/user-attachments/assets/1f01b39f-a105-4a45-99db-71cf4cf332f5)

주요 기능
-----
● TPU를 사용하여 학습

● 데이터 로딩 및 전처리 : COVID-19 관련 폐 질환 이미지를 OpenCV를 사용하여 로드하고 , RGB로 변환 후 , 해당 이미지와 관련된 마스크를 함께 저장

● 데이터 증강 : Tensorflow의 tf.keras.Sequential을 활용하여 U-Net에 효과적인 데이터 증강 기법 사용(랜덤 회전 , 랜덤플립)

● Tensorflow 데이터셋 생성 : tf.data.Dataset API를 사용하여 이미지를 텐서플로우 데이터셋으로 변환하고, 전처리 및 증강 작업을 적용

배치 처리와 데이터 프리패치를 통해 성능 최적화

● U-Net 모델 설계 : U-Net 아키텍처를 기반으로 한 모델을 정의. 인코더와 디코더 구조로 구성되어 있으며, 각 레이어에서 배치 정규화 및 활성화 함수를 사용하여 성능 개선

● 학습률 스케줄링 : 코사인 스케줄링을 사용하여 학습률을 점진적으로 감소시킴으로써, 모델이 더 안정적이고 효과적으로 수렴하며, 과적합을 방지할 수 있도록 유도

● 모델 컴파일 및 훈련 : Adam 옵티마이저와 sparse_categorical_crossentropy 손실 함수를 사용하여 모델을 컴파일

조기 중단(Early Stopping)콜백을 설정하여 검증 손실이 개선되지 않을 경우 훈련 조기 종료

개발 환경
-----
● Google Colab : 클라우드 기반 Python 개발 환경으로 , TPU를 사용한 딥러닝 모델 학습에 사용

● Python : 주요 프로그래밍 언어로 사용

● Google Drive : 데이터를 저장하고 불러오는 파일 시스템으로 사용

기술 스택
----
● Tensorflow & Keras : 딥러닝 모델 구축 및 학습을 위해 사용. U-Net 모델과 데이터 증강 기법 사용

● OpenCV : 이미지 전처리 및 변환에 사용(이미지 파일 로드 및 색상 변환 등)

● Scikit-learn : 학습 데이터와 검증 데이터를 분리하는 데 사용 (train_test_split 함수)

● Matplotlib : 학습 과정에서의 정확도 및 손실 그래프 시각화

● tf.data API : Tensorflow 데이터셋 생성 및 배치 처리에 사용

● Data Augmentation : U-Net에 효과적인 랜덤 회전 , 수평 플립을 사용하여 데이터 증강

성능 평가
----
![image](https://github.com/user-attachments/assets/9e430255-7f45-40c4-88ed-cd8e9ebf6a2f)

● 훈련과 검증 정확도가 각각 96%, 95% ,  손실이 각각 9% 13%에 도달

● 메모리 부족 현상이 없다면 이미지 사이즈 및 배치 사이즈 등 다른 하이퍼파라미터를 조정하여 더 좋은 성능을 얻을 수 있을거라고 추정

이미지 예측
---
![image](https://github.com/user-attachments/assets/861862a1-aa85-44d6-bd18-6fd0313358a1)


