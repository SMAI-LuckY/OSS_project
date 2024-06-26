# 손말톡톡 | 농인과 청인간의 소통 지원 🤝
#### 숙명여자대학교 인공지능공학부 OSS_project 27팀(LuckY) 🍀

---

## 1. 프로젝트 소개 🖥️
수많은 수어 관련 프로젝트들을 봤지만, 단순하게 단어를 번역해주는 프로젝트들만 다수 존재할 뿐, 실시간으로 소통이 가능하도록 하는 프로젝트는 보지 못함.수어는 음성으로, 음성은 텍스트로 번역함으로서 하나의 단말기로 농인과 비장애인이 소통할 수 있도록 하고자 함.

---

## 2. 개발 과정 ⏰
✅ 기간: 2024. 05. 21 ~ 2024. 06. 20
- 아이디어 노트 작성
- 제안서 작성
- 학습 데이터 수집(aihub)
- 수집 데이터 전처리(동영상 -> 이미지)
- 이미지 학습 -> 모델 선정
- 모델 -> 서비스 구현

✅ Skills & Tools

<img src="https://img.shields.io/badge/Visual Studio Code-007ACC?style=flat-square&logo=Visual Studio Code&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/>

![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)

![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)

![Babel](https://img.shields.io/badge/Babel-F9DC3e?style=for-the-badge&logo=babel&logoColor=black)



---

## 3. 개발자 소개 📍
- **팀장 최예인(2310165)** : 학습 데이터 수집, 수집 데이터 전처리, 학습 데이터 적용
- **박예린(2311475)** : 학습 데이터 수집, 수집 데이터 전처리, 이미지 학습
- **신소연(2311787)** : 학습 데이터 수집, 수집 데이터 전처리, 이미지 학습
- **차서연(2314865)** : 학습 데이터 수집, 수집 데이터 전처리, 이미지 학습


![팀원소개](https://github.com/SMAI-LuckY/OSS_project/blob/main/%ED%8C%80%EC%9B%90%EC%86%8C%EA%B0%9C.png)

---

## 4. For Users

#### 1️⃣ 프로젝트 구성
청인과 농인이 하나의 단말기를 통해 실시간으로 소통할 수 있는 수어 통역 어플리케이션을 개발하고자 함. 본 프로젝트에서는 농인의 수어 동영상(비디오 신호) 기반의 음성 생성 기술 개발을 
목표로 함. 자주 쓰거나 쉬운 단어 기준 .json 확장자의 단어로 학습. 학습할 데이터는 전처리 하여 이용함. 프론트엔드 부분도 제작해 보았으나, 가상환경에서의 서버 구축에 어려움이 있어 연결하지 못하였다.

- 키포인트 학습 모델 ResNet        
         1. 시공간지도사상기법을 통해 데이터를 학습.
         2. Mediapipe 이용하여 이미지 별 keypoint 추출.
         3. keypoint를 정규화 후 컬러이미지 변환.
          : AI-hub에서 다운받은 자료들은 깔끔하게 정제되어있는 데이터들이 많아 실제 
           사용할 때 학습에 넣을 데이터와는 다름. 따라서 좌표값 보정 필요. 
           정규화를 통해 모든 키포인트를 0~1 사이의 값으로 만듦.

#### 5️⃣ 버그 및 디버그

키포인트 학습 트러블 슈팅

문제 : 기존의계획은 AIHub에서 제공하는 keypoint를 사용해 모델을 학습시키고 결과값을 예측하려고 했으나, 동일한  영상에대해 mediapipe로 뽑은 keypoint와 Hub에서 제공하는 keypoint가 다르고, 프레임별로 keypoint가 존재하기 때문에 데이터의 양이 방대하여 학습에 많은 시간이 소요됨

해결 : keypoint의 형식을 맞추기 위해 주어진 keypoint를 사용하지 않고 직접 원천데이터에서 keypoint를 추출하고, 프레임별로 주어지는 point값들을 압축하기 위해 각 keypoint의 x, y, score 값을 매핑하여 하나의 이미지에 전체 프레임에 대한 정보를 담아 이를 학습시킴

#### 6️⃣ 참고 및 출처
- https://github.com/DEVOCEAN-YOUNG-404/HandTalker
- https://github.com/google-ai-edge/mediapipe
- https://vrworld.tistory.com/12

 



