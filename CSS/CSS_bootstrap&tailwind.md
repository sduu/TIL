# bootstrap

## bootstrap editor (자동화 툴)
- [bootstrap-editors](https://soshace.com/top-5-free-bootstrap-editors-tools/)
- [bootstrapstudio](https://bootstrapstudio.io/) (개발자가 사용하진 않음)

<br>

## 부트스트랩 테마 
- [theme forest](https://themeforest.net/)
- [wrapbootstrap](https://wrapbootstrap.com/)

<br>

## plugin
- sweetalert2(경고 메시지) -> dist안에 min(js, css)
    - [SweetAlert2](https://sweetalert2.github.io/)
- bootstrap-datepicker cdn
    - [bootstrap-datepicker](https://github.com/uxsolutions/bootstrap-datepicker)
- jQuery datepicker
    - [Datepicker](https://jqueryui.com/datepicker/)
- WYSIWYG editor
    - [summernote](https://summernote.org/) - 5버전 지원 X
    - [toast ui editor](https://ui.toast.com/tui-editor) 사용하세요.(bootstrap은 아님)
- bootstrap selector

<br>

## 부트스트랩 외주
- 모객 : 지인, 회사, (크몽같은 서비스는 부담)
- 호스팅 비용 산정
- 계약서 필히 작성 (나중에 문제가 생기는 경우가 꼭 1~2번은 있습니다.)
    - 저는 그런적이 없지만 완성이 안되서 생기는 문제
    - 완성 되었으나 기능을 추가해야 해서 생기는 문제
    - 만족을 못해 입금을 안해서 생기는 문제
    - (1억 이상) 완벽하게 완성 되었으나, 손배로 사업적으로 이득을 챙기려 해서 생기는 문제
- 스택
    1. 부트스트랩 + php + mysql
    2. 부트스트랩 + 워드프레스 (워드프레스는 DIVI 테마와 Pods 플러그인)
    3. 부트스트랩 + Node, express
    4. 부트스트랩 + Django

<br>

## 자동화순
1. bootstrap
2. tailwindcss
3. tachyons

<br>

# Tailwind

## Sizing

[Adding Custom Styles - Tailwind CSS](https://tailwindcss.com/docs/adding-custom-styles#using-arbitrary-values)

```html
<!-- 1 = 0.25rem -->

<div class="space-y-8"></div> <!--0.25rem * 8 -->
<div class="w-96"></div> <!--0.25rem * 96 -->
<div class="w-1/4"></div> <!-- 백분율 기반 -->
```

<br>

## Color

[Background Color - Tailwind CSS](https://tailwindcss.com/docs/background-color)

```html
<button class="bg-indigo-500"></button>
```

<br>

## Typography

[Font Family - Tailwind CSS](https://tailwindcss.com/docs/font-family)

[Text Color - Tailwind CSS](https://tailwindcss.com/docs/text-color)

[List Style Type - Tailwind CSS](https://tailwindcss.com/docs/list-style-type)

```html
<ul class="list-none list-inside">
    <li>hello world</li>
    <li>hello world</li>
</ul>
```

<br>

## Shadows

[Box Shadow - Tailwind CSS](https://tailwindcss.com/docs/box-shadow)

```html
<div class="grid grid-cols-2 gap-6">
    <div class="shadow-sm bg-white">shadow-sm</div>
    <div class="shadow bg-white">shadow</div>
    <div class="shadow-md bg-white">shadow-md</div>
    <div class="shadow-lg bg-white">shadow-lg</div>
    <div class="shadow-xl bg-white">shadow-xl</div>
    <div class="shadow-2xl bg-white">shadow-2xl</div>
    <div class="shadow-inner bg-white">shadow-inner</div>
</div>
```

<br>

## Spacing

[Padding - Tailwind CSS](https://tailwindcss.com/docs/padding)

[Margin - Tailwind CSS](https://tailwindcss.com/docs/margin)

[Space Between - Tailwind CSS](https://tailwindcss.com/docs/space)

```html
<div class="p-3">hello world</div>
<div class="pt-3">hello world</div>
<div class="my-8">hello worl</div> <!-- y축 방향 margin -->
<div class="flex flex-col space-y-4"> <!-- 자식 요소 사이 간격 -->
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```

<br>

## Borders

[Border Radius - Tailwind CSS](https://tailwindcss.com/docs/border-radius)

[Border Width - Tailwind CSS](https://tailwindcss.com/docs/border-width)

```html
<div class="rounded"></div>
<div class="rounded-md"></div>
<button class="rounded-full"></button>
<div class="border-2 border-indigo-600"></div> <!-- border는 pixel 단위를 사용 -->
```

<br>

## arbitrary value

[Adding Custom Styles - Tailwind CSS](https://tailwindcss.com/docs/adding-custom-styles#using-arbitrary-values)

주어진 값 외에 다른 값을 사용하고 싶을 때에는 arbitrary value를 사용할 수 있다.

```html
<div class="bg-[#bada55] text-[22px] before:content-['Festivus']"></div>

<div class="bg-[url('/what_a_rush.png')]"></div>
```

<br>

## flex & grid

[Flex - Tailwind CSS](https://tailwindcss.com/docs/flex)

[Gap - Tailwind CSS](https://tailwindcss.com/docs/gap)

[Grid Template Columns - Tailwind CSS](https://tailwindcss.com/docs/grid-template-columns)

```html
<div class="flex flex-wrap flex-col justify-center items-center gap-4">
    <div class="flex-1">hello</div> <!-- flex: 1 1 0% -->
    <div class="flex-auto">hello</div> <!-- flex: 1 1 auto -->
    <div class="flex-initial">hello</div> <!-- flex: 0 1 auto -->
    <div class="grow">hello</div>
</div>

<div class="grid grid-cols-4 grid-rows-3 grid-flow-col gap-2">
    <div class="col-span-2">hello</div>
    <div class="col-span-2">hello</div>
    <div class="">hello</div>
    <div class="">hello</div>
    <div class="">hello</div>
    <div class="">hello</div>
</div>
```

<br>

## transition

[Transition Property - Tailwind CSS](https://tailwindcss.com/docs/transition-property)

```html
<button class="transition ease-in-out delay-150 bg-blue-500 hover:-translate-y-1 hover:scale-110 hover:bg-indigo-500 duration-300">Save Changes</button>
```

<br>

## animation


[Animation - Tailwind CSS](https://tailwindcss.com/docs/animation)

```html
<div class="animate-spin"></div>
<div class="animate-ping"></div>
<div class="animate-pulse"></div>
<div class="animate-bounce"></div>
<div class="animate-[wiggle_1s_ease-in-out_infinite]"></div>
```

<br>

## 유틸리티 클래스 추가 설정

[Functions & Directives - Tailwind CSS](https://tailwindcss.com/docs/functions-and-directives#apply)

```html
<style>
.grid-i{
    @apply border-4 border-blue-500;
}
</style>
<div class="grid-i">hello</div>
<div class="grid-i">hello</div>
<div class="grid-i">hello</div>
```

> [Tailwind Play](https://play.tailwindcss.com/) <br>
> 위 사이트에서 라이브 테스트가 가능하다.

<br>

## 반응형

[Handling Hover, Focus, and Other States - Tailwind CSS](https://tailwindcss.com/docs/hover-focus-and-other-states#media-queries)

[https://tailwindcss.com/docs/responsive-design](https://tailwindcss.com/docs/responsive-design)

| sm | @media (min-width: 640px) |
| --- | --- |
| md | @media (min-width: 768px) |
| lg | @media (min-width: 1024px) |
| xl | @media (min-width: 1280px) |
| 2xl | @media (min-width: 1536px) |
| dark | @media (prefers-color-scheme: dark) |

```html
<div class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-6">hello world</div>
```

<br>

## SVG

[Heroicons](https://heroicons.com/)

Heroicons : Tailwind CSS의 제작자가 만든 아이콘 제공 서비스다. SVG, JSX 포맷의 아이콘을 클립보드 복사를 통해 간편하게 사용할 수 있다.

<br>

## 플러그인

[@tailwindcss/typography - Tailwind CSS](https://tailwindcss.com/docs/typography-plugin)

<br>

## 접근성

```html
<span class="sr-only">Settings</span>
```

<br>

## cheat sheet

[Tailwind CSS Cheat Sheet](https://nerdcave.com/tailwind-cheat-sheet)
