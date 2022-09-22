## 레티나 디스플레이

### 레티나란?

특정한 시야 거리에서 인간의 눈으로는 화소를 구분할 수 없는 화소 밀도(300 PPI가 넘을 경우)를 가진 애플 LCD 제품의 브랜드 이름

<br>

### 레티나(고해상도) 디스플레이에서 이미지가 흐려지는 이유는 무엇일까?

**화면을 구성하는 최소 단위인 픽셀의 두 가지 종류**

- 논리 픽셀 : CSS 픽셀<br>
ex ) 아이폰 4에서 CSS로 표현할 수 있는 값은 320 x 480
- 물리 픽셀 : 디바이스가 실제로 처리할 수 있는 화소의 기본 단위<br>
ex ) 아이폰 4이 구현하는 실제 해상도는 640 x 960 (2배 밀도 ratio 2)

<br>

**만약 아이폰4에 디자인 작업을 할 때 320px의 디자인 파일을 받아서 작업을 하게 된다면?**

브라우저는 CSS에서 정의한 픽셀만큼 이미지를 렌더링 해야하기 때문에 원래는 물리 픽셀에 맞게 렌더링된 이미지가 논리 픽셀 만큼 커지므로 흐린 이미지를 보여준다.

<br>

### 해결 방법

1. 2배수 이미지를 준비한다.<br>
ex) `168 x 84` 사이즈 이미지

1. 2배수 이미지를 1배수 이미지로 조정하여 사용한다.<br>
ex) `background-size: 84px 42px`