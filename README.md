# Pygame-Engine

## 프로젝트 개요

### **Air Hockey Engine**

![1.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/7ac2481c-c7f3-40e7-b710-fbef3f3444f9/1.png)

![asd.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/15e28d24-d07f-4e37-b071-829703f5fd69/asd.png)

### **Physics**

- 두 원 및 원과 직선 사이의 충돌 처리

### **Artificial Intelligence**

- 강화 학습 알고리즘을 통해 골키퍼 인공지능 구현

## 제작 목표

### **Physics : 두 원 및 원과 직선 사이의 충돌 처리**

- 두 원이나 원과 직선 간의 충돌을 정확하게 감지하고, 이에 대한 적절한 처리 로직을 구현하는 것이 목표. 이는 게임에서 오브젝트 간 상호작용과 충돌 감지가 중요한 부분이기 때문임
- 또한, 충돌 감지 알고리즘을 효율적으로 구현하여 게임의 성능을 유지하면서도 충돌 감지의 정확성을 보장하는 것이 중요하므로 최적화된 알고리즘을 선택하고 구현하여 게임의 부드러운 동작을 지원하고자 함

### **Artificial Intelligence : 강화 학습 알고리즘을 통해 골키퍼 인공지능 구현**

- 주어진 환경에서 골키퍼의 행동을 결정하는 데 강화 학습 알고리즘을 적용함. 주로 사용되는 알고리즘 중 하나인 Monte Carlo Method를 선택하여 골키퍼의 행동을 학습하고 개선함
- 또한, 게임 엔진 내에서 실시간으로 골키퍼의 학습과 평가를 수행함. 학습된 골키퍼는 실제 게임 플레이를 통해 경험을 쌓고, 그에 따라 행동을 조정하고 개선하게 됨

## 디자인&구조

- 플레이어(초록색)은 키보드 WASD를 통해 각각 좌, 상, 하, 우로 이동할 수 있음
- 골키퍼 AI(빨간색)은 주로 골대 근처에서 공을 수비함
- 공(검정색)은 플레이어/골키퍼 및 벽에 충돌 시 튕김
- 골대 내의 공간에 공이 닿으면 게임 종료
- 강화 학습을 통해 학습된 정책만을 남기고, 학습 시 사용된 코드는 주석 처리함

## 특징 설명

### Physics

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/163cb109-a679-4d62-a8c4-364906f482b7/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/60e179bb-889d-4f3f-9a0a-330243086809/Untitled.png)

> 두 원의 중심 사이 거리에서 각각읜 원의 반지름 합을 빼준 값인 음수라면, 두 객체가 겹쳐 있다는 의미이기 때문에 두 객체가 충돌했다고 판정함
> 

### **Artificial Intelligence**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/7cb2fa00-1729-4edf-977c-51619fe222ae/Untitled.png)

> 강화 학습(Reinforcement Learning)은 에이전트가 환경과 상호작용하며, 시행착오를 통해 보상을 최대화하기 위한 학습 방법론임. 이는 명시적으로 제공된 데이터 없이, 행동을 통해 어떤 환경에서 보상을 최대화하는 방법을 학습하는 데 사용됨. 따라서, 다양한 문제에 유연하게 적용 가능하며, 실제 상황에서의 의사 결정 과정을 모델링하고 학습하는 데 사용됨
> 

## 코드 설명

![1 (2).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/9c356189-ebce-4ebd-912a-35d411d90972/1_(2).png)

<aside>
➡️ Circle, Line Class 정의

</aside>

![ㅁㄴㅇㅁㄴㅇㅁ.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/c9efd511-ce28-4d59-a9f3-fae8e6ef1245/%E3%85%81%E3%84%B4%E3%85%87%E3%85%81%E3%84%B4%E3%85%87%E3%85%81.png)

<aside>
➡️ Player : 키보드를 통한 조작 (WASD)

</aside>

![2.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/a0ef7e1d-0534-47af-a04b-caec4d334c19/2.png)

<aside>
➡️ Circle의 position 및 초기 velocity 정의

</aside>

![4.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/782b3808-f714-42d9-ad2d-ffaea7624c3a/4.png)

![7.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/87982893-8f34-4f25-b997-4b4dcdd994fc/7.png)

<aside>
➡️ Circle 사이의 충돌 판정 & 처리

</aside>

![5.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/c4d23dfe-f4c2-4289-977e-0d97b09f4830/5.png)

<aside>
➡️ Circle(공)과 Line의 충돌 판정 및 처리

</aside>

![6.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/f39f3d7f-bbd4-45e1-b6c7-e317e767401b/6.png)

<aside>
➡️ Circle(Platyer&AI)과 Line의 충돌 판정 및 처리
→ 공은 Line과 충돌했을 시에 튕겨야 하지만, Player/AI는 Line과 충돌 시에 튕기지 않아야 함

</aside>

![8.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/f4401229-1615-4078-a0ff-ab34774cb62f/8.png)

<aside>
➡️ GoalkeeprEnv : Gym의 Env 클래스를 상속받는 게임 환경 클래스

- __init__ : 게임 환경의 상태 공간과 행동 공간을 설정. 여기서 상태 공간은 0 또는 1의 이산 공간이며, 행동 공간은 0 또는 1의 이산 공간으로 정의함
- step : 에이전트가 취한 행동을 받아서 환경을 업데이트하고, 새로운 상태, 보상, 종료 여부 및 추가 정보를 반환
- reset : 환경을 초기화하고 초기 상태를 반환
</aside>

![9.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/019fec14-ccb6-432d-9fd2-936ea3a61056/9.png)

<aside>
➡️ MC Control 알고리즘 구현

- 초기에 행동-가치 함수 Q와 반환값 저장을 위한 dictionary returns를 초기화
- 각 에피소드마다 환경을 초기화하고, 에이전트의 행동을 결정하여 에피소드를 진행
- 각 에피소드에서 받은 보상을 바탕으로 행동-가치 함수 Q를 업데이트
- 최종적으로 학습된 행동-가치 함수 Q를 반환
</aside>

![10.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4ebb0ace-caab-466c-b744-9d9d2a294213/59be1454-9b9d-4b22-8b57-3ea0c948df00/10.png)

<aside>
➡️ 앞서 정의한 GoalkeepEnv 환경을 생성하고, mc_control 함수를 호출하여 해당 환경에서 10,000번의 에피소드를 통해 학습된 행동-가치 함수 trained_Q를 출력

</aside>

## 실행 영상

https://youtu.be/5Q9zbiPL-os

## 실행 환경

- Python 3.11.4
