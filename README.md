## 애니메이션 동작 화면
- 라이브러리 없이 직접 JavaScript로 구현함

https://github.com/user-attachments/assets/6c6d4d33-1ee4-4580-bf2c-4186964b74c3

### 구현 세부 사항
- 드래그 후 마우스 커서 이동 시 실시간으로 모든 카드들의 transform 값을 계산하고 적용
  - 실시간으로 DOM을 직접 조작하여 애니메이션을 구현할 수도 있지만, 조작하는 비용이 매우 비싸고 실제 DOM 조작은 드롭 시에만 일어나면 된다고 판단함
  - 따라서 드래그 중에는 CSS의 transition 속성을 사용하여 애니메이션을 구현함
- 마우스 드롭 시, 내려놓을 지점의 인덱스(x, y)를 계산함
- Controller가 (x, y)를 계산하고 Model의 상태를 변경함
- Model은 상태 변경시 구독 중인 View를 호출함
- View는 Model로부터 변경을 받아 DOM API로 실제 DOM TREE를 조작함
- 위와 같은 흐름으로 MVC 패턴을 적용함
