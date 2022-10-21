# Diet_service-Object_detection
Alpaco Object detection mini project
### 🥗Introduction
1. 주제선정 이유 
- 바쁜 현대사회 속 1인 가구가 증가함에 따라 배달음식의 수요가 증가
- 바쁘다보니 식습관을 제대로 신경쓰지 않는 경향을 보임
- 이로인한 영양 불균형 문제 및 비만 환자수 증가
- 건강관리 및 제대로 된 식단 관리가 필요한데 실제로 잘 이루어지지 않아 이를 해결하기위해 프로젝트를 진행
2. 기존 다이어트 어플
- 건강관리 솔루션이라기보다 오직 체중 감량에 집중된 경향
- 또한 식단관리 어플은 사용자가 직접 식단을 입력하고 관리하는 수고로운 방식
3. 목표
- 음식사진을 찍으면 음식객체를 인식하는 모델을 만들어 그에 해당되는 음식 종류와 칼로리, 영양정보가 나오게 하는 보다 편리하고 직관적인 방법으로 식단관리를 할 수 있는 방안을 고려.

### 🥗Materials and Methods
1. Dataset
- http://foodcam.mobi/
- 12,000개의 이미지
- 총 100개의 class
- 한식, 일식, 양식등의 데이터로 이루어짐
- multiple food-item, single food-item으로 구성
2. Methods
- stage 1의 YOLOv4 모델 사용
- MS COCO dataset으로 pretrained된 weight를 갖고 전이학습

### 🥗Results
FIGURE1) single food item images </br>
![화면 캡처 2022-10-21 132141](https://user-images.githubusercontent.com/61971952/197111491-faa4f2a5-7084-4fa9-8969-5b4f2bea136f.png)
FIGURE2) multi food item images </br>
![multi](https://user-images.githubusercontent.com/61971952/197111640-57b6a349-492c-4272-adb0-1b199fe1a1c3.png)
FIGURE3) detecting food and kcal </br>
![칼로리](https://user-images.githubusercontent.com/61971952/197111756-f2d5e2c3-f166-497c-9103-508b9a595e7c.png)

### 🥗Discussion
- 클래스 하나당 충분히 학습을 시키켜야했는데 클래스 수가 너무 많아 그러지 못해서 정확도가 좀 떨어졌다.
- realtime이지만 정확도가 낮은 YOLO가 아닌 정확도가 좀 더 좋은 2stage방식을 사용하면 정확도가 더 높아질 수 있지 않을까 싶다.
- 앞으로의 활용가능성: </br>
① 오늘 하루 먹은 음식에서 부족한 영양소, 칼로리에 대한 안내, 맞춤형 식단 추천에 쓰일 수 있을 것. </br>
② 최근 삼성에서 나온 AI 냉장고인 비스포크는 안에 있는 식재료를 스스로 파악해 맞춤형 식단을 추천하는 등의 기능을 가짐.  </br>
이와 연결해 그날 아침과 점심으로 먹었던 것들 중 단백질과 비타민이 적정량보다 덜 먹었다면 이를 보완할 수 있는 정밀한 개인 맞춤형 식단을 제공하는 것이 가능할 것.
