# CSS

## 09. Text

### line-height

![01](https://user-images.githubusercontent.com/46313348/190399313-5041040e-48e7-4d8c-a331-858bf34fd507.png)

line-height = font-size + half-leading + half-leading

- `line-height: normal` : 폰트의 종류에 따라 크기가 달라진다.
- `line-height: 1` : 폰트 사이즈만큼 줄어들어 leading area를 제거할 수 있다.

<br>

**`line-height`의 값 `1`과 `1em`의 차이**

부모 요소에 1em을 주었을 경우에는 단순히 부모의 폰트 사이즈에서 em을 계산한 값이 자식 요소에 그대로 상속이 된다.

1을 주었을 때는 `line-height: 1`이 상속되는 것이기 때문에 부모의 사이즈가 어떻든 자식 요소의 폰트사이즈에 따라 달라진다.

<br>

> 💡 `:root` 와 `html`의 차이
> 
> `:root`를 쓰는 것은 루트의 가상요소를 선택한 것으로 `html`을 쓰는 것과 차이가 없다.
> 
> 강사님께서 `:root` 를 쓰는 것은 루트 요소를 선택한다는 것을 좀 더 명시적으로 작성한 것이라고 하셨다.

<br>

### text-overflow 
여러줄 말줄임 코드
```css
p {
  overflow: hidden;
  display:-webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
```
> 💡 **여러줄 말줄임 코드에는 ellipsis 속성값이 없는데 여러줄 말줄임이 가능한 이유**
> 
> Like line-clamp, -webkit-line-clamp is a shorthand of max-lines, continue, and block-ellipsis, except that
> 
> https://www.w3.org/TR/css-overflow-3/#propdef--webkit-line-clamp

<br>

## 11. Float
`float` 속성은 그림을 따라 흐르는 텍스트 레이아웃을 웹에서 구현하기 위해 탄생한 속성이다.

<br>

**`float`을 사용하면 부모 요소가 자식 박스의 존재를 인식하지 못하는 이유**

대부분의 요소들은 normal flow에 따라 레이아웃이 결정된다.

하지만 float, position(absolute, fixed 등)의 방법을 사용하면 normal flow에서 벗어나게 된다.

normal flow에 속한 요소들은 normal flow에서 벗어난 float, position 속성이 적용된 요소들을 인식하지 못한다.

<br>

**위 문제점을 해결하는 방법**
- BFC를 생성해서 float 속성이 적용된 요소를 컨테이너가 인식하도록 만들어준다.
    - overflow: visible 을 제외한 속성값(auto, hidden, scroll)을 사용
    - display: table-cell, inline-block, flow-root
    - position:absolute, fixed 등
- 부모 요소의 높이 값을 직접 지정해준다.
- clear 속성 사용
- clear-fix
    ```css
    .wrap::after {
        content:'';
        display:block;
        clear:both;
    }
    ```

<br>

> 💡 Block Formatting Context 더 알아보기
>
> [https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
>
> [https://www.w3.org/TR/CSS21/visuren.html#normal-flow](https://www.w3.org/TR/CSS21/visuren.html#normal-flow)
