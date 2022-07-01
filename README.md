# 📸 딥페이크 감지 모델 비교 프로젝트
Deepfake Detection using Image Crop and Image recognition
( 2022.04.01 ~ 2022.05.30 )

## 프로젝트 소개
최근 인공지능 기술이 발전하면서 딥페이크(Deepfakes) 기술이 점점 대두가 되고 있다. 딥페이크(Deepfake)란, 인공지능 기술인 딥러닝(Deep learning)과 ‘가짜’를 의미하는 단어인 페이크(fake)의 합성어로, 인공지능 기술을 이용하여 진위 여부를 구별하기 어려운 가짜 이미지나 영상물을 뜻한다. 딥페이크라는 2017년, 미국 온라인 커뮤니티 Reddit의 한 회원이 기존 영상에 유명인의 얼굴을 입혀 가짜 콘텐츠를 게재한 데서 유래가 되었다. 하지만 이 딥페이크 기술들이 언론 조작 및  음란물 생성에 사용되면서 딥페이크 기술의 문제점이 붉어지고 있다. 이런 문제점들에 맞춰 다양한 딥페이크 판별 어플리케이션, 시스템들이 생겨나고 있는 추세이다. 이런 추세에 맞춰 “딥페이크 변조 영상 탐지” 프로젝트를 진행하게 되었다. 
<br>
본 프로젝트는 여러 영상 데이터셋 속에서 image deepfake와 sound deepfake 영상을 찾아낸다. 딥페이크 영상을 탐지하기 위해 Resnet과 Facenet를 모델로 사용하였다. 최종적으로 학습한 두 모델의 정확도를 구하여, 이를 비교함으로써, 어느 모델이 더 정확한 탐지를 하는지에 대해 연구해보고자 한다. 
.<br>

## 깃허브 폴더 구조

```Deepfake-Detection-Project
├── dataset
│   ├── mtcnn_resnet
│   └── mtcnn_facenet
├── models
│   ├── train.py
│   ├── classify.py
│   ├── model.py
│   └── dataset.py
├── mtcnn_resnet
├── mtcnn_facenet
```

## 사용 데이터
본 프로젝트는 kaggle에서 개최한 ‘Deepfake Detection Challenge’에서 제공하는 데이터셋을 기반으로 진행하였다. 데이터셋은 딥페이크 처리된 fake 영상들, 딥페이크 처리되지 않은 real 영상들과 함께 영상들의 fake와 real 여부가 정리되어 있는 파일로 구성되었다. MTCNN과  Resnet 모델을 사용하여 데이터셋 속  400개 영상들의 얼굴 객체 탐지를 진행하였고 딥페이크 처리 여부를 확인하였다. 400개의 영상들을 한 번에 모델에 사용하기 힘든 경우에는 모델에 사용할 수 있는 최대한의 영상들을 랜덤하게 선정하여 데이터셋으로 사용하였다.
<br>

MTCNN과 Facenet 모델에 사용한 데이터셋의 경우, 앞서 사용한 동영상 데이터셋을 이미지 데이터셋으로 전환하여 사용하였다. 영상에서 이미지를 추출하는 코드를 사용하여 영상당 한 개의 이미지를 추출하였다. 추출한 400개의 이미지들을 train set과 validation set에 8:2의 비율로 분류했으며, 기존에 제공된 파일을 참고하여 fake와 real 여부를 분류하였다. 그 결과 train set은 56개의 real 이미지들과 264개의 fake 이미지들로 구성하였고,  validation set은 20개의 real 이미지들과 60개의 fake 이미지들로 구성하였다. 그러나 real과 fake 이미지 수의 불균형이 심한 점을 고려하여 train set은 class 당 56개를, validation set은 class 당 20개를 랜덤하게 선정하여 프로젝트를 진행하였다.
<br>



## 사용 모델

- [Facenet](https://drive.google.com/drive/folders/12aMYASGCKvDdkygSv1yQq8ns03AStDO) <br>
- [Resnet,MTCNN](https://github.com/timesler/facenet-pytorch/tree/master/models)



## 참고 문헌

- [MTCCN](https://arxiv.org/abs/1604.02878) <br>
- [Facenet](https://jkisaaclee.kro.kr/keras/facenet/deep%20learning/computer%20vision/2019/10/01/how_to_develop_a_face_recognition_system_using_facenet_in_keras_ko/)




