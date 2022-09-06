# HTML

> 💡 주석 <br>
> 포트폴리오를 제작할 때는 작성 의도와 코드를 설명하는 주석을 꼼꼼하게 작성하자

<br>

## 7. Text-level semantics

### 텍스트 레벨 요소의 특징

- 컨텐츠 크기만큼 영역을 차지한다.
- 자식으로 Sections, Grouping Contents 를 배치할 수 없다.

<br>

### `<br>`, `<wbr>`

- `br` : 줄 바꿈
- `wbr` : 텍스트 사이에 위치하여 줄 바꿈 할 위치를 표시<br>
ex) 사용자가 URL이 끝난 것으로 혼동하지 않도록 문장 부호 이전에 줄 바꿈
    
    ```html
    <p>https://developer.mozilla<br>.org/ko/docs/Web/HTML<br>/Element/wbr</p>
    <p>https://developer.mozilla.org/ko/docs/Web/HTML/Element/wbr</p>
    ```
    
<br>


> 💡 **CSS `word-break`** <br>
> 텍스트가 콘텐츠 박스 밖으로 벗어날 경우 어떤 식으로 줄 바꿈 해줄지 지정 하는 속성
> - `word-break: normal` : CJK 문자는 글자 기준으로, CJK 이외의 문자는 단어 기준으로 줄 바꿈
> - `word-break: break-all` : 글자 기준으로 줄 바꿈
> - `word-break: keep-all` : 단어 기준으로 줄 바꿈


> 💡 **CSS `white-space`** <br>
> 요소가 공백 문자를 처리하는 방법을 지정 하는 속성
> - `white-space: break-all` : 콘텐츠 박스 밖으로 벗어날 경우 줄 바꿈
> - `white-space: nowrap` : 줄 바꿈은 `<br>` 요소에서만 일어남
> - `white-space: pre` : `pre` 태그를 사용했을 때처럼 연속 공백을 유지

<br>

### `<a href="경로">`

- 하이퍼 텍스트 즉, 링크를 만들 때 사용한다.
- `a` 태그에 `href` 속성을 작성해야 하는 이유는?<br>
: `href`속성이 없는 `a` 요소에는 TAB키로 포커스가 생기지 않아 접근성에 위배된다.<br>
: 검색엔진은 페이지를 해석할 때 `a` 요소의 `href` 속성을 통해서 어디를 향하는 지를 판단하기 때문에 SEO와도 관련이 있다.
- 예외적으로 앵커 태그는 Sections, grouping content 요소의 자식으로 하는 것이 허용된다.

<br>

> 💡 **하이퍼 텍스트란?**<br>
> HTML를 이어주는 핵심적인 요소<br>
> 책이 아교와 끈으로 이어져 있다면 HTML은 하이퍼 텍스트로 이어져 있는 거대한 책이다.<br>
> 읽어볼 만한 링크 [https://www.snugarchive.com/blog/what-is-html/](https://www.snugarchive.com/blog/what-is-html/)

<br>

```html
<a href="https://www.naver.com">click</a>

<!-- 새 창 열림 -->
<a href="https://www.naver.com" target="_blank">click</a>

<!-- 현재 경로를 기준으로 index.html 찾기 -->
<a href="./index.html">click</a>

<!-- 해쉬 링크 : 페이지 내부에서 #three 로 이동 / ID 만 사용 가능 -->
<a href="#three">click</a> 

<!-- index.html 다운로드 / Internet Explorer는 download 속성을 지원하지 않는다.-->
<a href="./index.html" download>click</a>

<!-- hello.hwp 파일이 존재하면 브라우저에서 실행 -->
<a href="./hello.hwp">hwp click</a>

<!-- hello.hwp 파일의 이름을 a.hwp로 지정해서 다운로드 -->
<a href="./hello.hwp" download="a.hwp">hwp download click</a>

<a href="./hello.pdf">pdf click</a>

<a href="./hello.pdf" download="a.pdf">pdf download click</a>

<!-- 통화 연결 -->
<a href="tel:+82027777777">(02)777-7777</a>

<!-- 메일 발신 -->
<a href="mailto:hello@gmail.com">hello@gmail.com</a>
```
<br>

➕ CSS 내부 링크 스크롤 부드럽게 이동하기<br>
[https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior)
```css
html {
	scroll-behavior: smooth;
}
```

<br>

### `<b>, <strong>`

- `b` : 의미 없이 굵은 글꼴을 표현한다.
- `strong` : 중요성을 강조한다는 의미로 사용한다.


> 💡 `<b>` 와 같이 의미 없이 스타일링만을 위한 태그가 있는 이유가 무엇일까?<br>
> `<b>` 태그는 시맨틱 태그가 나오기 이전에 개발된 것으로 과거에 CSS가 생기기 전에는 HTML으로 스타일링을 하기도 했었다.

<br>

### `<i>, <em>`

- `i` : 기울임 글꼴을 표현한다. HTML5부터는 기술 용어, 외국어 구절, 등장인물의 생각 등을 표현하기 위해 사용한다.
- `em` : 기울임 글꼴을 표현하며 강조의 의미가 있다.

<br>

> 💡 `strong` 과 `em` 의 차이는?
> `strong` 은 강한 강조 `em` 은 약한 강조

<br>

### `<dfn>`

- definition(정의)의 약자로 용어를 정의할 때 사용한다.
- `<dfn>`에서 가장 가까운 부모가 `<p>`, `<dt>` `<dd>` , `<section>` 인 경우 그 부모 요소의 콘텐츠를 용어의 설명으로 간주한다.
- 논문에서 주석을 다는 것처럼 문서에서 최초로 나타났을 때 사용한다.

```html
<dl>
  <dt><dfn>RSS</dfn> flibbit </dt>
  <dd>An XML format for ...</dd>
</dl>
```

<br>

### `<abbr>`

- abbreviation(축약형)의 약자로 준말 또는 약자를 정의할 때 사용한다.
- `title` 속성을 사용하면 준말의 전체 뜻이나 설명을 툴팁으로 제공할 수 있다.
    
    ![220906-1](https://user-images.githubusercontent.com/46313348/188638477-8b225d5f-c656-43ee-9ee2-8a2d030abcf1.png)
    
<br>

### `<sup>, <sub>`

- `sup` : 윗첨자
- `sub` : 아래 첨자
    
    ![220906-2](https://user-images.githubusercontent.com/46313348/188638482-32644285-c975-4ebb-814e-663624a08914.png)
    
<br>

### `<span>`

- 줄 바꿈 없이 영역을 묶는 용도

<br>

## 모두의 HTML/CSS 과제 피드백

(주석 확인)

<br>

## 8. Embedded content

> 💡 무료 이미지 사이트
> [https://pixabay.com/ko/](https://pixabay.com/ko/)
> [https://unsplash.com/](https://unsplash.com/)

> 💡 무료 폰트 사이트
> [https://noonnu.cc/](https://noonnu.cc/)
> [https://fonts.google.com/](https://fonts.google.com/)

<br>

### `<img>`

> 💡 이미지와 폰트는 저작권을 꼭 확인하자. 브로커가 있으니 주의😨<br>
> **이미지**<br>
> : 상업적 용도 사용 가능, 출처 안 밝혀도 되는 경우만 사용 / 상업적 용도로 사용하여 돈을 벌었는지가 주요 쟁점<br>
> **폰트**<br>
> : 무료폰트도 개인 무료 폰트와 상업 용도 무료 폰트로 나누어짐 / 가능하면 대기업 무료 폰트 사용을 권장 / 저작권을 확인하기<br>

<br>

### `alt` (alternative text)

```html
<!-- 스크린 리더가 파일명을 읽는다 -->
<img src="img/a.jpg">

<!-- 스크린 리더가 읽지 않는다 -->
<img src="img/a.jpg" alt="">

<!-- 스크린 리더가 alt 값을 읽는다 -->
<img src="img/a.jpg" alt="스크린 리더가 읽어야 하는 문구">
```

<br>

### `src` (source)

1개의 이미지 소스를 명시하는 속성이다.

- 절대 경로 : 현재 파일 위치와 관련 없이 열 수 있는 경로 
ex) URL, 폴더 트리
- 상대 경로 : 지금 열려 있는 폴더 기준

<br>

### 반응형 이미지를 위한 `srcset`

**`srcset`**

- 해상도에 따라 이미지의 크기를 조절해서 브라우저가 최상의 이미지를 로딩하는데 도움을 준다.
- 이미지 소스의 세트라는 의미로 같은 비율의 **다양한 크기를 가지는 동일 이미지**를 **최소 2개** 이상 명시하는 속성이다.
- 브라우저에 이미지 선택권을 위임하는 속성이다.

<br>

**반응형 이미지 만들기**

- `srcset` : 브라우저에게 제시할 이미지 목록과 그 크기를 지정 / 작은 크기 이미지부터 순서대로 입력
- `sizes` : 뷰포트의 조건에 따라 이미지가 출력 될 사이즈를 지정 / 미디어 조건문을 정의하고 그 조건이 참일 때 출력할 최적 크기를 입력
- `src` : `srcset`을 사용할 수 없는 브라우저에서는 `src`로 이미지를 출력하기 때문에 필수로 작성
- x서술자 : 디바이스의 화소 밀도에 따라 이미지를 로딩하도록 브라우저에 알림
- w서술자 : 원본 이미지의 가로 너비를 브라우저에게 알림. 400 x 300(px)의 w 값은 400w


> 💡 w서술자와 x서술자는 동시에 사용할 수 없다.

> 💡 웹표준을 준수하기 위해 `srcset` 속성을 사용하면 그에 맞는 `sizes` 속성을 반드시 명시해야함

> 💡 화소의 밀도(pixel density)<br>
> 화소의 개수가 많을수록 더 높은 해상도의 기기이다. 개발자 도구의 콘솔창에`window.devicePixelRatio` 를 입력해서 사용하고 있는 화면의 화소 밀도를 알 수 있다.

<br>

**예시**

```html
<img
srcset="img/a.png 700w,
        img/b.png 600w,
        img/c.png 300w"
sizes="(min-width: 960px) 250px,
        (min-width: 620px) 150px,
        300px"
src="a.png"
alt="test">
```

위 코드의 결과 : 

뷰포트 너비가 960px 이상일 때 원본이 700px인 이미지 `a.png` 가 250px로 사용된다.

뷰포트 너비가 620px 이상일 때 원본이 600px인 이미지 `b.png` 가 150px로 사용된다.

뷰포트 너비가 619px 이하일 때 원본이 300px인 이미지 `c.png` 가 300px로 사용된다.

<br>


> 💡 `sizes` 속성이 작성되어도 CSS가 우선으로 적용되기 때문에 이미지 사이즈를 컨트롤 할 때 충돌이 생길 수 있다.
또한 `sizes`와 `width`를 같이 작성 할 경우도 `width` 속성이 우선이다.

> 💡 HTML로 반응형 이미지를 만드는 방법은 협업 시 어려움이 있을 수 있다. 반응형 이미지를 처리하는 방법은 사전에 동료와 커뮤니케이션 하자.

> 💡 참조
> [https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/](https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/)

<br>

### 반응형 이미지 `<picture>`

**`picture`**

- 서로 다른 디스플레이나 기기에서 여러 개의 이미지 중에서 적절한 이미지를 사용할 수 있도록 해준다.
- 이미지 포맷 자체를 변경 할 수 있다.

<br>

**반응형 이미지 만들기**

- `<source>` 요소들의 속성 값을 각각 확인해 나가며 조건을 만족하는 첫 번째 `<source>` 요소를 사용
- `<img>` 요소 : `<picture>` 요소를 지원하지 않는 브라우저를 위한 하위 호환성(backward compatibility)을 위해 사용되거나 명시된 `<source>` 요소가 모두 조건을 만족하지 못 할 경우 사용 / 때문에 최신 포맷의 이미지를 지원하고 싶다면 크로스 브라우징을 위해 `<picture>` 요소와 함께 사용 하는 것이 좋음(점진적 향상기법)
- `media` 속성 : 이미지를 출력할 미디어 조건문을 정의
- `type` 속성 : 이미지의 포맷 타입을 브라우저에게 알림


>💡 점진적 향상기법<br>
>예전 기술 환경에서 동작할 수 있는 기능을 구현해두고, 최신 기술을 사용할 수 있는 환경에서는 최신 기술을 제공하여 더 나은 사용자 경험을 제공할 수 있는 방법

<br>

**예시**

```html
<picture>
    <source srcset="babies_large.jpeg" media="(min-width:960px)">
    <source srcset="babies.jpeg" media="(min-width:620px)">
    <!-- 기본 이미지 -->
    <img src="babies_small.jpeg" alt="귀여운 아기 팽귄들">
</picture>
```

<br>

> 💡 `picutre` VS `srcset`<br>
> 반응형 이미지
> [https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images](https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
