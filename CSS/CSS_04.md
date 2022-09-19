# CSS

## 14. Flex

### justify-content

주축(Axis)을 기준으로 정렬

<br>

### align-items

교차축(cross-axis)을 기준으로 정렬

<br>

### align-content

아이템들이 여러 줄일 때 교차축(cross-axis)을 기준으로 정렬

<br>

### flex-basis

아이템의 기본 크기

1.  주 축(`flex-direction`)에 따라 `flex-basis`가 넓이가 되기도 하고, 높이가 되기도 한다.
2. `width` 와 `flex-basis` 를 동시에 적용할 경우 `flex-basis`가 우선순위를 가지게 된다.
3. `width` 는 너비를 강제한다. `flex-basis` 는 내부의 컨텐츠에 따라 유연한 크기를 가진다.

<br>

### flex-grow

초깃값: 0

`flex-grow`에 지정된 숫자 = `flex-basis`를 제외한 여백 부분의 비율

![1](https://user-images.githubusercontent.com/46313348/190998219-22b31791-5e15-4c87-933e-33512e09839c.png)

<br>

### flex-shrink

초깃값 : 1

`flex-basis` 의 반대되는 개념

아이템이 `flex-basis`의 값보다 작아질 수 있는지를 결정

`flex-shrink: 0` 을 주면 아이템의 크기가 `flex-basis`보다 작아지지 않아 고정폭을 가진다.

> 💡 W3C 에 따르면 basis, grow, shrink 은 축약 속성인 `flex`를 사용하는 것을 권장한다.


```css
.item {
  flex: 1;
  /* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
  flex: 1 1 auto;
  /* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
  flex: 1 500px;
  /* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```

<br>

### flex-item 에 사용하는 속성

- `align-self` : 개별 flex-item의 교차 축(cross-axis) 정렬
- `order` : 개별 flex-item의 배치 순서를 결정. 크기가 클 수록 뒤에 배치된다.
    
    [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Ordering_Flex_Items#use_cases_for_order](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Ordering_Flex_Items#use_cases_for_order)
    

> 💡 `order`를 이용해 순서를 바꾸는 것은 시각적인 순서일 뿐, 스크린 리더로 화면을 읽을 때는 HTML 마크업 순서대로 읽는다.

<br>

## 15. Grid

![2](https://user-images.githubusercontent.com/46313348/190998223-033af0d5-04ae-478c-add1-22ae7abac4ea.png)

<br>

### grid-template-rows

행(row)방향 그리드 트랙의 높이를 설정

```css
.container {
  display: grid;

  /* column */
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-columns: 5% 10% 15% 70%;
  grid-template-columns: 100px 200px;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-columns: repeat(3, 1fr);
}
```

<br>


### grid-template-columns

열(column)방향 그리드 트랙의 너비를 설정

```css
.container {
  display: grid;

  /* row */
  grid-template-rows: 100px;
  grid-template-rows: repeat(3, 100px);
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-rows: 100px 200px 100px 200px;
  grid-template-rows: repeat(3, 100px 200px);
}
```

> 💡 fr : 비율을 의미하는 fraction의 약자 (분수, 일부, 비율)

<br>

### repeat () 함수

repeat(반복 횟수, 반복 값)

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, 100px 200px);
}
```

### minmax() 함수

최솟값과 최댓값을 지정할 수 있는 함수

```css
/* 열방향 그리드 트랙의 최소 넓이를 50px, 최대 넓이를 150px로 한다 */
grid-template-columns: repeat(3, minmax(50px, 150px));

/* 행방향 그리드 트랙의 최소 높이를 120px, 최대 높이를 가용할 수 있는 최대 크기로 한다 */
grid-template-rows: repeat(3, minmax(120px, auto));
```
<br>

### auto-fill & auto-fit

```css
grid-template-columns: repeat(3, minmax(50px, 150px));
grid-template-columns: repeat(auto-fill, minmax(50px, auto));
/* grid-template-columns: repeat(auto-fit, minmax(50px, auto)); */
```

배치할 수 있는 그리드 셀이 없을 때 속성의 역할을 확인할 수 있다.

`auto-fill` 컬럼의 남는 공간을 채우지 않는다.

`auto-fit` 컬럼의 남는 공간을 채우기 위해 요소의 너비가 늘어난다.

<br>

### gap

셀과 셀사이의 간격을 설정한다.

```css
.container {
  /* 이전 버전 */
  row-gap: 10px;
  column-gap: 20px;
}

.container {
  gap: 10px 20px;
  /* row-gap: 10px; column-gap: 20px; */
}

.container {
  /* 브라우저 호환을 위해 이전 버전과 같이 적기도 한다. */
  grid-gap: 20px;
  gap: 20px;
}
```


> 💡 `gap` 속성은 IE를 지원하지 않는다.

<br>

### (grid-item에 사용하는 속성)

### grid area 설정하기

![3](https://user-images.githubusercontent.com/46313348/190998222-13c03e66-7bbb-499a-9385-9a7aadf82667.png)

<br>

- `grid-column`, `grid-row` : grid-line의 번호를 이용

```css
.item:nth-child(1) {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 2;
}

/* 축약형 */
.item:nth-child(1) {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}

/* 축약형 2 */
.item:nth-child(1) {
  /* grid-row-start, grid-column-start, grid-row-end, grid-column-end */
  grid-area : 1 / 1 / 3 / 3;
}
```
<br>

- `span` 키워드 : grid-line의 번호를 사용하지 않고 몇 개의 셀을 차지하게 할 것인지를 지정

```css
.item:nth-child(1) {
  grid-area: 1 / 1 / span 2 / span 2;
}
```

<br>

- `grid-template-areas` : 영역 이름으로 그리드 정의
- `grid-area` : 요소에 영역 이름을 지정

```css
body {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-areas:
        '.       .      .      time'
        'header  header header header'
        'aside-l main   main   aside-r'
        'footer  footer footer footer';
}
time {
    grid-area: time;
    background-color: blanchedalmond;
}
header {
    grid-area: header;
    background-color: pink;
}
main {
    grid-area: main;
    background-color: royalblue;
}
.aside-left {
    grid-area: aside-l;
    background-color: lightgreen;
}
.aside-right {
    grid-area: aside-r;
    background-color: lightgreen;
}
footer {
    grid-area: footer;
    background-color: aquamarine;
}
```
