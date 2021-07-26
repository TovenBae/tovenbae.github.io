---
title: "Unity 학습하기"
date: 2021-07-05 16:37:28 -0400
categories: Unity
---

# Unity 학습하기

#### 참고사이트
- 학습
    - [Unity 입문하기](https://coding-groot.tistory.com/33)
- 샘플
    - [타워디펜스 게임](https://github.com/myodan/tower-defense-game)


## 기본개념
### Scene
Scene은 한국어로 장면입니다. 유니티에서도 똑같이 하나의 레벨 또는 스테이지를 뜻 합니다. 하나하나의 Scene 파일들에 우리가 만들어가는 게임 장면들이 들어갑니다. 

### GameObject
Hierarchy창에 있는 모든 애들이 게임 오브젝트입니다. Main Camera, Directional Light, 제가 방금 추가한 House, Sphere 모두 다 게임 오브젝트입니다.

유니티에서 게임 오브젝트는 한마디로 Box입니다. 기능을 담는 박스입니다

### Component
Component는 한국어로 구성요소라는 뜻입니다. 게임 오브젝트의 구성요소라는 뜻입니다. 제가 위에서 게임 오브젝트는 여러 가지 기능들을 구성요소로 하는 Box라고 말했습니다. 그 각각의 기능들을 유니티에서는 Component라고 부릅니다. 

**종류**
- Collider : 게임 오브젝트가 충돌할 수 있게 함
- Camera : 게임을 실행했을 때 볼 창
- Sound Listener : 사운드가 들리는 곳 설정
- Transform : 위치, 회전, 크기 등의 조정
- Rigidbody : 물리적인 상호작용
- Script : 사용자 정의 기능, 주로 C# 사용
    -  Start() 메서드

        유니티가 자동으로 호출해주는 메서드 중 하나입니다.
        게임이 시작할 때 딱 한 번만 호출됩니다.
        Update() 메서드가 호출되기 직전에 호출됩니다.
        주로, 초기화와 같은 작업을 할 때 많이 쓰게 됩니다.
    - Update() 메서드

        유니티가 자동으로 호출해주는 메서드 중 하나입니다.
        매 프레임마다 호출됩니다.
        Frame이란?
        혹시 FPS(Frame Per Second)라는 것을 들어보셨나요?
        N FPS라는 말은 1초마다 N개의 Frame이 일어난다라는 뜻입니다.
        예를 들어서, 60 FPS이면 1초에 60번 Update 메서드가 호출됩니다.

### Prefab 사용
Ref : [유니티 객체 회전 및 프리펩 사용](https://multicore-it.com/91?category=686217)

프리팹(Prefab)은 씬에서 객체를 생성하는 템플릿으로 사용할 수 있는 에셋 타입
- 동일한 프리팹으로 생성된 객체는 한꺼번에 속성을 변경할 수 있다
- 프리팹을 생성하기 위해서는 먼저 프로젝트 뷰에서 폴더를 생성하고 이름을 Prefabs로 변경한 후에 계층 뷰에 있는 객체를 Prefabs 폴더로 드래그 앤 드랍으로 가져오면 된다. 이제 프로젝트 뷰에서 객체를 복사(Duplicate)하면 하나의 프리팹을 사용하여 객체가 생성되기 때문에 나중에 속성을 쉽게 변경할 수 있다. Target 객체의 인스펙터 뷰를 보면 객체 이름 하단에 Prefeb이 생성된 것을 볼 수 있다.

### Unity Script
- Debug.Log : 콘솔창에 메시지 출력
- Time.deltaTime : 이전 프레임에서 현재 프레임이 일어나까지 걸린 시간. 컴퓨터 성능과 무관하게 프레임간의 간격으로 동작하도록 함.
- Transform : GameObject 이동 
    . 모든 Object는 Transform을 가짐
    . Object의 위치, 회전, 크기을 저장하고 다루기 위해서 사용
- GetComponent<원하는컴포넌트>() : 해당 스크립트가 부착된 게임 오브젝트로부터 원하는 컴포넌트 가져오기
- Rigidbody : GameObject 이동
    . 모든 Object가 물리 제어로 동작하게 함.
    . Mass : 질량, Drag : 공기 저항, Angular Drag : 토크로 회전할 때 공기 저항이 영향을 미치는 정도, Use Gravity : 중력 작용 여부, Is Kinematic : 물리 엔진으로 제어되지 않고 오로지 Transform으로만 조작
    . 속도 변경 : GetComponent<Rigidbody>().Velocity = 벡터;
    . 힘 적용 : GetComponent<Rigidbody>().AddForce(벡터)
- 스크립트 외부의 게임 오브젝트 접근 : 스크립트가 부착되지 않는 다른 게임 오브젝트 접근
    1. Find("게임오브젝트 이름") : 이름으로 찾기, Hierarchy내 기술된 게임오브젝트 이름
    2. FindGameObjectWithTag("Tag명") : 게임 오브젝트 속성설정하는 Inspector에서 Tag명을 부여한 게임 오브젝트
- 모든 자식들 접근하기
    . 선택한 게임 오브젝트 바로 아래에 있는 자식만 iterate하는 경우
    > foreach (Transform child in transform) {
    >   Debug.Log(child.name);   
    > }
    > 
    . 선택한 게임 오브젝트 아래에 있는 모든 자식을 iterate 하는 경우
    > Transform[] allChildren = GetComponentsInChildren<Transform>();
    > foreach (Transform child in allChildren) {
    >     // 자기 자신의 경우엔 무시, 게임오브젝트명이 다르다는 가정
    >     if (child.name == transform.name)
    >         return;
    >     Debug.Log(child.name);
    > }

### 유니티 물리 충돌 처리 : Collider
Ref : [유니티 물리 충돌 처리](https://multicore-it.com/92?category=686217)

콜라이더(Collider) 컴포넌트는 오브젝트의 물리 충돌을 처리하는 역할을 한다. 물리 충돌 처리 관점에서 게임 오브젝트는 4가지 종류로 나눌 수 있다.
**유형**
- 정적 콜라이더(Static Collider) : 콜라이더(Trigger 비활성화) + No Rigidbody
    - 콜라이더가 있지만 리지드바디가 없는 게임 오브젝트
    - 움직이지 않는 벽, 바닥 등에 사용
    - 움직이지 않는 다고 가정함.
- 리지드바디 콜라이더(Rigidbody Collider) : 콜라이더(Trigger 비활성화) + 리지드바디(Kinematic 비활성화)
    - 콜라이더와 리지드바디 컴포넌트가 함께 있는 게임 오브젝트
    - 물지적인 충돌과 함계 힘에 의해 반응
- 키네메틱 리지드바디 콜라이더(Kinematic Rigidbody Collider) : 콜라이드(Trigger 비활성화) + 리지드바디(Kinematic 활성화)
    - 콜라이더와 리지드바드 컴포넌트가 함께 있으며 특별히 Kinematic 옵션이 활성화되어 있는 오브젝트
    - 물리적 힘이나 충돌에 반응하지 않고 스크립트를 통해 움직임
    - 평소에는 정적 콜라이더와 같이 동작하지만 상황에 따라 반응하는 방문이나 창문과 같은 객체에 사용할 수 있다.
- 트리거(Trigger) : 콜라이더(Trigger 활성화)
    - 콜라이더에 Trigger 속성이 활성화된 객체
    - 단단한 객체로 동작하지 않고 물체를 단순히 통과 시키는 역할
    - Trigger로 설정된 객체에 다른 객체가 들어오면 OnTriggerEnter 함수를 호출
    - 콜라이더 컴포넌트에 트리거가 활성화 된 상태에서 리지드바디 컴포넌트가 추가되면 물리적 충돌 체크를 못하기 때문에 물체는 바닥에 서있지 못하고 바닥으로 가라 앉는다
    - 이 때는 일반적으로 리지드바디 컴포넌트의 키네메틱을 활성화시켜(Use Gravity를 비활성화 시킬 수도 있다) 중력이 작용하지 못하도록 한다.

**충돌처리 방식**
- Trigger 사용
    - 객체의 콜라이더(Collider) 컴포넌트에 있는 Trigger 속성이 활성화되어 있으면 물체가 충돌할 때 OnTriggerEnter 함수가 호출
    - 충돌이 계속되는 시점에는 OnTriggerStay 함수가 반복적으로 호출되며 충돌이 끝나면 OnTriggerExit 함수가 호출
- Collision 사용
    - 객체의 Collision 컴포넌트에 Trigger 속성이 비활성화되어 있을 경우 두 객체가 충돌하면 OnCollisionEnter 함수가 호출
    - 충돌이 계속되는 시점에는 OnCollisionStay 함수가 호출되며 충돌이 끝나면 OnCollisionExit함수가 호출

Trigger와 Collision을 차이점은 Collision 충돌 처리 할 때는 두 객체 모두 리짓바디(Ridgidbody) 컴포넌트의 Kinematic 속성이 비활성화되어 있어야 한다는 것이다.

Trigger는 단단한 객체로 동작하지 않기 때문에 Kinematic 제약이 적용되지 않는다. 따라서 충돌을 검사해야 하는 객체의 특성에 따라 어떤 방식을 사용할 지 선택하면 된다.

![Trigger 객체충돌처리1](https://t1.daumcdn.net/cfile/tistory/9999C9365BF40E860B)
![Trigger 객체충돌처리2](https://t1.daumcdn.net/cfile/tistory/99BCFF365BF40E8602)

### 유니티 화면에 텍스트 표현하기
Ref : [유니티 화면에 텍스트 표현하기](https://multicore-it.com/93?category=686217)

![텍스트 객체 생성](https://t1.daumcdn.net/cfile/tistory/990447335BF40F6B28)

![텍스트 표현을 위한 스크립트](https://t1.daumcdn.net/cfile/tistory/994A05335BF40F6C2E)