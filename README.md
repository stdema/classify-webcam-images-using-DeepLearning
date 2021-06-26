Deep Learning에 대한 기본 지식을 이해하기 위해 MATLAB®에서 제공하는 Deep Learning Toolbox를 사용

# - 딥러닝을 사용하여 웹캠 영상 분류하기

이 예제에서는 사전 훈련된 심층 컨벌루션 신경망 GoogLeNet을 사용하여 웹캠의 영상을 실시간으로 분류하는 방법을 보여줍니다.

MATLAB®과 간단한 웹캠 및 심층 신경망을 사용하여 주변의 사물을 식별합니다. 이 예제에서는 사전 훈련된 심층 컨벌루션 신경망(CNN 또는 ConvNet) GoogLeNet을 사용합니다. 1백만 개가 넘는 영상에 대해 훈련된 GoogLeNet은 영상을 키보드, 커피 머그잔, 연필, 각종 동물 등 1,000가지 사물 범주로 분류할 수 있습니다. GoogLeNet을 다운로드하고 MATLAB을 사용하여 계속해서 카메라 영상을 실시간으로 처리할 수 있습니다.

GoogLeNet은 다양한 영상을 대표하는 다양한 특징을 학습했습니다. 영상을 입력값으로 받아 영상에 포함된 사물의 레이블과 각 사물 범주의 확률을 제공합니다. 주변의 사물을 사용하여 GoogLeNet이 영상을 얼마나 정확히 분류하는지 실험해 볼 수 있습니다. GoogLeNet의 사물 분류에 대해 자세히 알아보기 위해, 최종 결정된 클래스만 표시하는 대신 상위 5개의 클래스에 대한 점수를 실시간으로 표시할 수 있습니다.

# - 카메라와 사전 훈련된 신경망 불러오기

카메라에 연결하고 사전 훈련된 GoogLeNet 신경망을 불러옵니다. 이 단계에서는 임의의 사전 훈련된 신경망을 사용할 수 있습니다. 이 예제를 실행하려면 MATLAB Support Package for USB Webcams와 Deep Learning Toolbox™ Model for GoogLeNet Network가 필요합니다. 필요한 지원 패키지가 설치되어 있지 않으면 이를 다운로드할 수 있는 링크가 제공됩니다.

![image](https://user-images.githubusercontent.com/86040099/123497207-30955280-d667-11eb-88e9-439c220c27d3.png)

이 예제를 다시 실행하려면 먼저 clear camera 명령을 실행하십시오. 여기서 camera는 웹캠에 대한 연결입니다. 이렇게 하지 않으면 동일한 웹캠에 대한 또 하나의 연결을 만들 수 없기 때문에 오류가 표시됩니다.

# - 카메라의 스냅샷 분류하기

영상을 분류하려면 신경망의 입력 크기에 맞게 영상의 크기를 조정해야 합니다. 신경망 영상 입력 계층의 InputSize 속성의 처음 2개 요소를 가져옵니다. 영상 입력 계층은 신경망의 첫 번째 계층입니다.

![image](https://user-images.githubusercontent.com/86040099/123497253-5fabc400-d667-11eb-8be5-6c857d813163.png)

