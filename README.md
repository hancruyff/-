## 🗉목차
[1. 개요](#1-개요)

[2. 강화학습](#2-강화학습)

[3. 주요 코드](#3-⌨주요-코드)

[4. 결과](#4-결과)

## 1. 🎮개요

스타크래프트를 플레이하는 에이전트 개발

<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white"> <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=PyTorch&logoColor=white">

## 2. 🤖강화학습
<img src="https://github.com/user-attachments/assets/036926fe-0c6d-4c94-bdb9-70b1ae664467" width="500" height="300"/>

에이전트가 주어진 상황에서 최대한의 보상을 얻을 수 있는 행동을 선택하는 것

### q-learning 
<img src="https://github.com/user-attachments/assets/37c94158-a7bd-4974-9d90-b9d5653547b8" width="700" height="100"/>

테이블을 통해 Q함수를 찾아서 Q값을 이용하여 최적의 행동을 선택하는 방식


스타크래프트의 경우 Frozen Lake와 같은 단순한 게임과 달리 매우 복잡한 게임이라 Q-Learning을 사용하기 부적합

### DQN
Q-Learning과 신경망을 결합하여 상태의 복잡성으로 인해 


정확하게 구할 수 없는 Q함수를 신경망을 통해 근사화 한 뒤 Q값을 이용하여 최적의 행동을 선택


스타크래프트와 같은 복잡한 상태를 가진 문제를 해결하기 적합

## 3. ⌨️주요 코드
```
def __init__(self):
에이전트 초기화
```

```
def setup(self, obs_spec, action_spec):
환경을 설정하는 메서드 
```

```
def reset(self):
에피소드 처음에 호출되어 일부 상태 변수를 재설정하는 메서드
```

```
def step(self, obs):
매 에피소드의 타임스탭마다 호출되는 메서드
```

게임 속 다양한 정보는 obs.observation 객체를 통해 접근

### 🏗️에이전트 설계
<img src="https://github.com/user-attachments/assets/09612529-dcee-40d2-a126-5a2e25e7ed77" width="300" height="300"/>

에이전트가 선택할 수 있는 행동은  5가지

No-op : 아무것도 하지 않음


자원 채취 : SCV를 선택하여 미네랄을 채취


건물 생산 : SCV를 선택하여 서플라이 디포, 배럭 중 하나를 선택하여 건설


유닛 생산 : 커맨드 센터를 선택하여 SCV를 생산하거나 배럭을 선택하여 마린 생산


공격 : 마린을 선택하여 적을 공격


### 🧠학습
![317980205-4b6f1d97-b705-4b8d-a507-b13d6550cf10](https://github.com/user-attachments/assets/afbf3071-b302-4d00-ab57-083e5c5d685d)

봇을 상대로 학습시키고 테스트

## 4. 📊결과
![image (15)](https://github.com/user-attachments/assets/176f6031-b6fa-486f-a5e7-a2c0181dbceb)

80%이상의 승률을 기록
