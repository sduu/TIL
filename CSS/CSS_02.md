# CSS

## 8. CSS declarations

### 왜 `<html>` 과 `<body>` 에 `background-color` 를 부여하면  페이지 전체에 색상이 가득 채워질까?

![03](https://user-images.githubusercontent.com/46313348/189894840-41895dc3-8926-4cba-8381-aa966433f732.png)

- `<html>` 과 `<body>` 는 모두 block 요소이기 때문에 높이 값을 따로 지정하지 않으면 콘텐츠의 높이만큼 높이를 가진다. <br>그런데 왜 `<html>` 과 `<body>` 에 `background` 값을 부여하면 요소의 높이에 상관없이 문서 전체에 배경 색상 또는 이미지가 가득 채워지는 것일까?

- 그것은 CSS를 만든 사람의 의도가 담긴 결과이다. `<body>` 에 `background-color`를 지정하는 것을 전체 영역에 색상을 채우고 싶다는 의도로 판단하고 그것을 반영해 주는 것이다. 

- `<body>`에 `background` 값을 지정하면 Canvas라 불리는 `<body>` 너머의 어떤 영역으로 보내진다. `<body>` 요소의 크기 변화는 없는 상태로 Canvas에 `background` 의 컬러나 이미지가 칠해지면서 배경이 된다. `<body>` 의 상위 요소인 `<html>` 도 마찬가지이다. 

- 만약 `<body>` 와 `<html>`에 모두 `backgorund-color` 가 지정되면 `<body>` 는 더 이상 그 역할을 수행할 필요가 없어서 일반 요소가 되고, `<html>`의 `background-color`가 Canvas로 보내지게 된다.

![04](https://user-images.githubusercontent.com/46313348/189894841-bf58f62f-d224-4551-8c5d-47454aa00c99.png)


> 💡 종찬님의 강의
>
> [https://youtu.be/H7teKNwV-Bk](https://youtu.be/H7teKNwV-Bk)
>
> **추가 설명**
> 
> [https://www.w3.org/TR/CSS2/colors.html#background](https://www.w3.org/TR/CSS2/colors.html#background)
> 
> 
> ![02](https://user-images.githubusercontent.com/46313348/189894839-fe7188a3-f31e-4d0c-a08c-503278992307.png)
> 
> 루트 요소의 배경은 캔버스의 배경 이 되고 루트 요소 자체에 대해서만 칠해진 경우와 동일한 지점에 고정된( ['background-position' 의](https://www.w3.org/TR/CSS2/colors.html#propdef-background-position) [경우) 전체 캔버스 를 덮습니다.](https://www.w3.org/TR/CSS2/intro.html#canvas) 루트 요소는 이 배경을 다시 칠하지 않습니다.
> 
> 그러나 HTML 문서의 경우 작성자가 HTML 요소보다 BODY 요소의 배경을 지정하는 것이 좋습니다. [루트 요소가 'background-color' 에 대해 'transparent' 및](https://www.w3.org/TR/CSS2/colors.html#propdef-background-color) ['background-image'](https://www.w3.org/TR/CSS2/colors.html#propdef-background-image) 에 대해 'none' 값을 계산한 HTML "HTML" 요소 또는 XHTML "html" 요소인 문서의 경우 사용자 에이전트는 대신 다음을 사용해야 합니다. 캔버스의 배경을 칠할 때 해당 요소의 첫 번째 HTML "BODY" 요소 또는 XHTML "body" 요소 자식에서 배경 속성의 계산된 값이며 해당 자식 요소의 배경을 칠해서는 안 됩니다. 이러한 배경은 루트 요소에 대해서만 칠해진 경우와 동일한 지점에 고정되어야 합니다.
> 
> **Canvas**
> 
> [https://www.w3.org/TR/CSS2/intro.html#canvas](https://www.w3.org/TR/CSS2/intro.html#canvas)
> 
> ![01](https://user-images.githubusercontent.com/46313348/189894843-bb5ba352-45c4-4304-9b67-ecc8035f9337.png)
> 
> 모든 미디어에서 캔버스 라는 용어 는 "서식 구조가 렌더링되는 공간"을 설명합니다. 캔버스는 공간의 각 차원에 대해 무한하지만 렌더링은 일반적으로 대상 매체에 따라 사용자 에이전트에 의해 설정된 캔버스의 유한 영역 내에서 발생합니다. 예를 들어, 화면에 렌더링하는 사용자 에이전트는 일반적으로 최소 너비를 부과하고 뷰포트 의 크기에 따라 초기 너비를 선택합니다 . 페이지에 렌더링하는 사용자 에이전트는 일반적으로 너비와 높이 제약을 부과합니다. 청각적 사용자 에이전트는 오디오 공간에 제한을 가할 수 있지만 시간에는 제한을 두지 않습니다.

<br>

## 9. Text

### line-height 의 단위

- normal : 기본 값. 폰트의 `font-family`에 따른 글자의 기본 높이이다
- number : 1은 font-size 값 만큼의 라인 높이를 의미하고 2는 font-size 값의 두 배를 의미한다
- px : px로 고정된 값을 적용한다
- em : 부모 요소의 font-size에 비례한 값을 적용한다
- % : 요소 자신의 폰트 사이즈를 기준으로 값을 설정한다
