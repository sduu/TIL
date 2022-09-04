# 🙌프론트엔드 개발자가 하는일
프론트엔드 개발자는 접근성, SEO, 크로스 브라우징, HTML, CSS, JavaScript, 프론트엔드 프레임워크, 퍼포먼스 성능 등 다양한 작업을 한다.<br>
대부분의 최신 웹 사이트는 다이나믹한 UI로 구성되어 있어 프론트엔드 개발의 역할이 중요하다.<br>

🔗웹 퍼블리셔 vs 웹 프론트엔드
[https://hyeonseok.com/blog/306](https://hyeonseok.com/blog/306)

<br>

# 🎉HTML

> ```jsx
> <meta http-equiv="X-UA-Compatible" content="IE=edge">
> ```
> 💡 위 코드는 IE 호환 설정에 관한 메타데이터이기 때문에 필요에 따라 사용하자

<br>

## 5. Sections

### `<article>`

- 독립적으로 구분하거나 재 사용할 수 있는 컨텐츠를 담는다.
- `<h1>...<h6>` 태그가 꼭 포함 되어야 한다
- 위젯을 만들 때도 사용을 한다.
    
    ![01](https://user-images.githubusercontent.com/46313348/188293554-44e17580-c2fc-4343-b559-a01de6b621f3.png)

<br>

### `<section>`

- `<h1>...<h6>` 태그가 꼭 포함 되어야 한다
- 연관 있는 제목으로 그룹화할 수 있는 컨텐츠를 담는다.
    
    ![02](https://user-images.githubusercontent.com/46313348/188293563-6c094dea-ca99-4ab7-b170-37884327971d.png)

<br>

### `<header>`

- 특정 콘텐츠의 상단
    
    ![03](https://user-images.githubusercontent.com/46313348/188293562-0e2c8d03-4506-45fb-befd-b579004a6f0a.png)
    
- 주로 `<h1>` 태그(로고)가 포함되어 있다.

> 💡 Q&A <br>
> **Q**. 네이버나 다음 포탈에서 `nav`가 아닌 `div` 태그를 사용하는 이유 <br>
> **A**. HTML5 semantic elements는 비교적 최근에 생겼기때문에 지원하지 않는 브라우저가 있음. 대형 포탈은 사용자가 굉장히 다양하기 때문에 다양한 사용자에게 호환성을 지원하겠다는 의미로 `div`를 사용한 것일 수 있음.

<br>

### `<h1>...<h6>`

- 제목을 지정하며 중요도에 따라 순서대로 사용된다.
- 사용자가 페이지의 계층 구조를 쉽게 파악할 수 있게 해준다.
- 글씨 크기가 다른 이유는 브라우저에서 기본 css 스타일을 주었기 때문이다.
- `<h1>` 요소는 페이지당 한 번만 사용할 것을 권장한다.
- 익명 영역 : `<h1>...<h6>` 헤딩 태그 사이에 브라우저가 `<section>` 태그로 나눈 것 같이 나름대로 영역을 설정해준다. 하나의 주제를 가지는 임의의 영역으로 생각한다.
    
    ![04](https://user-images.githubusercontent.com/46313348/188293560-4fa25f3a-2c77-49ff-ac16-b64960749a58.png)
    
- `<hgroup>` 태그로 헤딩 그룹을 묶을 수 있다.

> 💡 Chrome의 HeadingMaps Extension으로 헤딩태그를 포함한 문서의 구조를 좀 더 쉽게 확인할 수 있다.

<br>

### `<nav>`

- 보통 눌렀을 때 다른 페이지로 이동하는 메뉴에 사용한다.
    
    ![05](https://user-images.githubusercontent.com/46313348/188293558-183ef4f4-924b-4af5-b984-894d2b7acecf.png)

<br>

### `<aside>`

- 보통 각주, 광고 영역에 사용한다.
    
    ![06](https://user-images.githubusercontent.com/46313348/188293557-68dfef76-6fdc-4b2a-8b5c-fa3f841b7bad.png)

<br>

### `<footer>`

- 주로 회사 정보, 저작권 등의 내용을 담는다.
    
    ![07](https://user-images.githubusercontent.com/46313348/188293556-e29a16db-084f-4629-9990-3875c725a4a4.png)

<br>

### `<adress>`

- `<body>` 태그 안에 존재하는 `<address>`는 해당 문서의 연락 정보를 나타낸다.
- `<article>` 태그 안에 존재하는 `<address>`는 해당 글에 대한 연락 정보를 나타낸다.
    
    ![08](https://user-images.githubusercontent.com/46313348/188293555-d271d5a2-221f-4f35-9f02-cac4a047d4e6.png)

<br>

## 6. Grouping content

### `<ol>` `<ul>` `<li>`
- 리스트 컨텐츠를 표현한다.
- `<ol>` 은 ordered list  `<ul>` 은 unordered list 의 약자다.
- `<li>` 요소는 `<ol>` `<ul>` 요소의 직계 자식으로 사용한다.
- 주로 `<li>` 요소로 담을 컨텐츠가 3가지 이상일 때 사용한다.

<br>

### `<dl>` `<dt>` `<dd>`
- 사전처럼 어떤 것을 정의할 때 쓰이는 목록이다.
- `<dl>` 은 definition list `<dt>` 는 definition term `<dd>` 는 definition description 의 약자다.
- 아래와 같은 구조도 가능하다.

```html
<dl>
  <div>
    <dt></dt>
    <dd></dd>
  </div>
</dl>
```
<br>

### `<div>`

- 레이아웃을 나눌 때 사용한다.

<br>

### `<figure>` `<figcaption>`

- 이미지와 이미지 캡션을 이어준다.

```html
<figure>
  <img src="images/baby.jpg" alt="엄마 코끼리와 아기 코끼리">
    <figcaption>
      관심 받고싶어하는 아기
    </figcaption>
</figure>
```

<br>

### `<p>`

- 하나의 완결된 문장, 문단을 표현한다.
- `<p>` 태그 안에 `<p>` 태그를 자식 요소로 사용하지 않는다.

<br>

### `<pre>`

- 주로 컴퓨터 코드를 표현할 때 사용한다.
- 작성된 내용 그대로 화면에 표시된다.
    
    ```html
    <pre>
      안녕하세요


      만나서 반갑습니다!
      <code>
        const a = 1;
      <code>
    </pre>
    ```

<br>

### `<blockquote>`
- 인용문 `<blockquote>`
- 인용구 `<q>`
- 출처 `<cite>`

<br>

### `<main>`

- 문서의 핵심 주제나 핵심 기능을 나타낸다. 
- 중복되는 내용이면 안된다.

<br>

### `<hr>`
- 원래는 가로줄을 표현하는 태그로 사용했지만, HTML5부터 콘텐츠의 주제가 변경되었을때 그 구별을 위한 태그로 사용한다.
- `<p>`태그 내 사용은 웹 표준에 어긋난다.

```html
<p>Lorem ipsum, dolor sit amet</p>

<hr>

<p>Lorem ipsum, dolor sit amet</p>
```

<br>

### 엔티티 코드 (Entity Code)
Html 문서에서 특수 문자를 입력하기 위해 사용하는 코드를 말한다.

**자주 사용되는 엔티티 코드**
- &amp; : `&amp;`
- &lt; : `&lt;`
- &gt; : `&gt;`
- &quot; : `&quot;`
 
**🔗더 다양한 엔티티 코드**
[https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references](https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references)

<br>

### 유니코드
세상의 모든 언어를 컴퓨터에서 일관되게 표현하기 위해 생긴 코드 체계를 말한다.<br>
🔗Unicode 14.0 Character Code Charts [http://www.unicode.org/charts/](http://www.unicode.org/charts/)
