# 파트1 CSS 꼭 알아야하는 기초 탐구

## 레이아웃 잡기

콘텐츠와 같은 세부적인 것에 집중하지 말고 전체를 보자. <br>
메인을 하나의 큰 덩어리로 생각하고 큰 요소에서 작은 요소로 이동하며 레이아웃을 잡아주자.

아래의 페이지는 몇 개의 덩어리로 이루어져 있을까?

![220902-1](https://user-images.githubusercontent.com/46313348/188156575-7538ddef-48e9-48dd-b6fe-b3266bf137ba.png)

<br>

## HTML 용어 소개

```html
<div></div>
```
`<div>` : 태그, 요소

>💡 **태그와 요소의 차이?** <br>
>태그는 태그 그 자체를 말하며 요소는 태그를 이용해 만든 구성 요소를 말한다.

<br>

## CSS 용어 소개

```css
div > a {
	background-color: orange;
}
```

`div` : Type Selector (유형 선택자)

`background-color` : Property (속성) 

`orange` : Value (값)

`>` : Combinator (결합자)

`:` : 구분자

`;` : 마침

<br>

> 💡 영문 명칭이 무엇인지 아는 것도 중요하다 <br>
> MDN 사이트를 활용해보기 <br>
> [https://developer.mozilla.org/ko/](https://developer.mozilla.org/ko/)

<br>

## CSS 초깃값 (initial value)

초깃값이란 속성을 별도로 지정해 주지 않았을 때 가지는 속성의 기본값을 말한다. 초깃값은 MDN에서 쉽게 확인 할 수 있다.

![220902-2](https://user-images.githubusercontent.com/46313348/188156572-bde5a907-2b64-41c4-ac6a-61da469d3ec4.png)

<br>

**block 요소의 너비**

요소의 `width`를 지정하지 않으면 기본 초깃값으로 `auto` 가 주어진다.

block 요소가 `width: auto` 인 경우에는 부모 요소로부터 주어진 사용 가능한 최대 너비를 가지게 된다.

<br>

**width: auto 와 width: 100% 의 차이**

- auto : 브라우저가 `margin`, `padding`, `border` 를 고려하여 유연하게 늘어난다.
- 100% : 브라우저가 100%를 단순히 픽셀 값으로 변환한다. `margin`, `padding`, `border` 의 값을 고려하지 못하고 크기가 늘어나기 때문에 부모 요소를 벗어날 수 있다.
- 참조 : [https://ishadeed.com/article/auto-css/?ref=sidebar](https://ishadeed.com/article/auto-css/?ref=sidebar)

<br>

**block 요소의 높이**

요소의 `height`를 지정하지 않으면 기본 초깃값으로 `auto` 가 주어진다.

block 요소가 `height: auto` 인 경우에는 콘텐츠의 양만큼 높이가 자동으로 잡힌다.

<br>

## 사용자 에이전트 스타일시트 (User agent stylesheet)

![220902-3](https://user-images.githubusercontent.com/46313348/188156570-6cd394dd-687b-431e-8f51-2becdfa45dc5.png)

크롬 개발자 도구로 `body` 를 살펴보면 user agent stylesheet 라는 문구로 내가 작성하지 않은 CSS Style이 적용되어 있는 것을 볼 수 있다. 

user agent stylesheet란 브라우저가 기본적으로 제공하는 스타일시트로, 각 브라우저마다 스타일이 다르다. <br>크로스 브라우징을 위해서 기본 스타일을 reset.css 등으로 초기화 해주는 작업이 필요하다.

🔗 Chrome User Agent Stylesheet 
[https://chromium.googlesource.com/chromium/src/third_party/+/master/blink/renderer/core/html/resources/html.css](https://chromium.googlesource.com/chromium/src/third_party/+/master/blink/renderer/core/html/resources/html.css)

<br>

## CSS 상속 (inheritance)

자식 요소에 CSS 속성을 지정하지 않은 경우 부모 요소에 적용된 스타일을 물려받는 것을 뜻한다.

<br>

**기본적으로 상속이 지원되는 속성**

`font-size`, `font-weight`, `font-style`, `text-align`, `text-decoration` 등

<br>

**CSS 상속 개념을 활용한 reset.css**

```css
/* Reset */
h1, p {
    margin: initial;
}

h1 {
    font-size: inherit;
    font-weight: inherit;
}
```

- User agent stylesheet 가 있는 속성 :  `initial`로 초기화
- User agent stylesheet 가 있고 상속이 지원되는 속성 : `inherit` 으로 초기화


<br>
<br>
<br>

# 파트2 클래스 셀렉터와 박스모델

## **CSS의 display 속성**

**block** 

- 혼자 한 줄을 다 차지한다
- `width`, `height`, `margin`, `padding` 속성이 모두 반영된다

**inline**

- 한 줄에 다른 요소와 함께 나란히 배치된다
- 콘텐츠의 크기 만큼만 공간을 차지하는 성격을 가지고 있다
- 컨테이너가 아니기 때문에 `width` `height` 개념이 존재하지 않는다
- `margin` 속성은 좌우 간격만 반영이 되고 상하 간격은 반영되지 않는다
- `padding` 속성은 간격은 반영되지만 상하 공간은 차지하지 않는다

**inline-block**

- **inline** 요소처럼 한 줄에 다른 요소와 함께 나란히 배치된다
- **block** 요소처럼 `width`, `height` 속성 지정 및 `margin`, `padding` 속성의 상하 간격이 반영된다
- text content의 존재 여부에 따라 baseline이 결정된다.
    - 빈 inline-block의 경우 margin-box의 하단이 baseline이 된다.
    - 텍스트가 담긴  inline-block의 경우 마지막 text content가 baseline이 된다.

> 💡 **inline 요소 간의 간격이 벌어지는 이유는?** <br>
> 이 간격은 마크업의 개행이 시각적으로 보이는 것으로 <br>
> 인간을 위해 식별이 용이하게 하도록 띄어쓰기 되는 것이다. <br>
> 폰트 사이즈에 따라 유동적인 간격이다.  <br>
> HTML은 시각적인 것을 담당하지 않으므로 CSS로 간격을 없애는 것을 권장한다. <br>

<br>

**block 요소를 중앙 정렬**

: 정렬할 요소에 `width: 300px; margin: 0 auto;`

>💡 땅으로 비유해서 이해하기 <br>
> - block 요소를 쓴다는 것은 한 줄의 전체 땅을 빌리는 것이며, `width` 를 고정하는 것은 그 너비만큼 땅에 집을 지은 것이라 할 수 있다. <br>
> - 남은 땅은 아직 사용하지 않았지만 여전히 해당 block 요소의 소속의 공간이다. (available space) 그래서 다음 div가 나와도 그 땅을 쓸 수 없다. <br>
> - `margin: auto` 는 집을 짓고 남은 땅의 크기를 여백으로 가진다는 의미이다. <br>
> - 좌우에 `margin: auto` 를 준다면 남은 공간을 둘로 나눠서 좌우로 나눠가지면서 가운데 정렬이 된다. <br>
> - 상하는 `margin: auto` 로 정렬이 되지 않는데 block 요소의 상하단은 다른 요소의 땅이므로 auto의 값이 0으로 계산된다. <br>

<br>

**inline 요소를 중앙 정렬**

: 정렬할 요소의 부모 요소에 `text-align: center;`

`text-align` 은 block 요소 안에 있는 inline 요소를 정렬한다.

<br>

## 클래스 셀렉터의 의해

클래스 셀렉터를 활용하여 공통분모와 플러스알파로 분류하여 코드를 작성하자.

![220902-4](https://user-images.githubusercontent.com/46313348/188156568-f069f57c-f7dd-48af-9885-a74521dfa320.png)


>💡<br>
>`border: 2px solid;`<br>
>`color: red;` <br>
>border의 color 속성 값으로 currentColor 키워드를 사용하면 color 속성의 값을 색상으로 가져온다. <br>
>여기서 currentColor는 생략이 가능하다.


<br>

## CSS 우선순위 (Selector Specificity)

**CSS Cascading**

CSS는 Cascading Style Sheet의 약자로

여기서 Cascading은 우선 순위에 따라 스타일이 적용되는 규칙을 말한다. 

<br>

**CSS 우선순위 점수**

명시도 점수가 높은 선언이 우선 적용된다. 같은 점수인 경우 나중에 선언한 것이 적용된다.

- 전체 선택자 * (Universal Selector), 부정 선택자 : 0, 0, 0, 0
- 타입 선택자 : 0, 0, 0, 1
- 클래스 선택자, 가상 선택자, 속성 선택자 : 0, 0, 1, 0
- 아이디 선택자 : 0, 1, 0, 0
- 인라인 스타일 : 1, 0, 0, 0
- !important : 최고 점수

```css
h1.wow {
 color: orange;
}

.wow.wow {
	color: purple
}
```

`h1.wow` 11점 `.wow.wow` 20점으로 color는 purple로 적용이 된다

<br>


>💡 VSCode 에서 Hover:Enabled 설정을 하면 에디터에서 Selector Specificity 점수를 확인할 수 있다.
>
>![220902-5](https://user-images.githubusercontent.com/46313348/188156556-06af1544-4853-4f5a-af90-3d1883e2a30c.png)
>
>![220902-6](https://user-images.githubusercontent.com/46313348/188156581-6ee228af-a160-46b7-95cf-09ac7f2d8b45.png)
>

<br>

## 마진 병합 현상

마진 병합 현상은 인접해 있는 block 요소 간의 상 하단 마진이 병합되는 이슈를 말한다.

```html
<!-- 형제간 마진 병합 -->
<style>
	.box1 {margin: 50px;}
	.box2 {margin: 50px;}
</style>
<div class="box1">box1</div>
<div class="box2">box2</div>

<!-- 부모 간 마진 병합 -->
<style>
	.container {
			/* overflow: hidden; 으로 해결 가능하다 */
	    background-color: lightsalmon;
	}
	.inner {
	    width: 400px;
	    height: 400px;
	    margin: 100px auto 0;
	    background-color: aquamarine;
	}
</style>
<div class="container">
	<div class="inner">
	</div>
</div>
```
