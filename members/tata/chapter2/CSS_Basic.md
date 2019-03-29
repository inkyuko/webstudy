# CSS Basic

CSS는 **Cascading Style Sheet**의 약자이다. CSS는 문서의 콘텐츠와 레이아웃, 글꼴 및 시각적 요소들로 표현되는 문서의 외관(디자인)을 분리하기 위한 목적으로 만들어졌다.  

CSS 명세는 World Wide Web Consortium에서 관리한다. CSS는 세 개의 주 레벨이 정의되어 있고 이 레벨들은 버전이나 세대라고 볼 수 있으며, 현재 CSS1, CSS2 및 CSS3가 정의되어 있다.  
   

# CSS 속성

-   여러 속성 값은 반드시 공백으로 구분되어야 한다.
-   축약 표현 속성은 여러 속성 값을 하나의 간소화된 선언으로 적용할 수 있다.
-   속성이 명시되지 않으면 해당 속성의 기본 값이 적용된다.
  
  

## CSS 속성의 주요 위치

-   하나의 규칙으로 여러 HTML 요소와 HTML 문서를 제어할 수 있기 때문에 대부분의 경우 외부 CSS 파일에 규칙을 정의하는 것을 선호한다.
-   HTML 주석 태그(`<!-- -->`)는 호환되지 않는 브라우저에서 CSS 코드를 숨기는 용도로 사용한다.

#### link 요소를 이용한 외부 CSS 파일

HTML의  `<link>`  태그를 이용하여 외부 파일을 포함한다.

```html
<head>
  <link href="style.css" rel="stylesheet" type="text/css">
</head>
```
##### import를 이용한 외부 CSS 파일

`@import`  CSS 선언을 이용하여 다음 위치에 외부 CSS 파일을 포함한다.

-   문서의  `<head>`  태그
-   다른 CSS 파일. 이 경우 하나의 CSS 파일이 여러 개의 다른 CSS 파일을 중첩하여 포함할 수 있다.

HTML

```html
<head>
  <style type="text/css">
  @import url(style.css); 
  </style>
</head>

```

##### HTML 문서의 head 태그

`<style>`  태그를 이용하여 CSS 규칙을 선언할 수 있다.

HTML

```html
<head>
  <style type="text/css">
  .logo {color: #eeeeee;} 
  </style>
</head>

```

##### HTML 요소에 인라인 스타일로 삽입

HTML의 style 속성을 이용하여 HTML 문서의  `<body>`  태그 내 요소들에 인라인 스타일을 지정한다.

HTML

```html
<body>
  <p style="height:100px; color:blue">
</body>
```

### CSS 기본 문법

CSS 규칙은 선택자(selector)와 선언부(declaration)로 나뉜다. 선언부는 다시 속성(property)과 속성값(value)로 나누게 된다.

![css 문법](https://t1.daumcdn.net/cfile/tistory/270CCE4255509FCB34)그림 출처 : http://www.w3schools.com/css/css_syntax.asp

-   선택자는 보통 스타일링하고 싶은 HTML 요소나 부여한 ID 혹은 class가 위치한다.
-   선언부에 여러개의 속성과 속성값이 있을때는 ;(세미콜론)으로 구분한다.
-   각각의 선언은 속성과 속성값을 :(콜론)으로 구분한다.

### CSS 우선순위

CSS는 기본적으로 선언된 순서에 따라 적용되지만 각종 선택자와 삽입 위치에 따라 우선순위가 달라질 수 있다.

#### 선택자 우선순위

!important > 인라인 스타일 > 아이디 선택자 > 클래스/속성/가상 선택자 > 태그 선택자 > 전체 선택자

경쟁 규칙이 같은 선택자 그룹에 속해 있다면 선택자의 종류와 수에 따라 우선순위가 결정된다. 즉 높은 우선순위의 선택자를 더 많이 사용한 규칙이 이긴다.

#### 삽입 위치 우선순위

1.  &lt;head&gt; 요소안의 style 요소
2.  &lt;style&gt; 요소안의 @import 문
3.  &lt;link&gt; 요소로 연결된 CSS 파일
4.  &lt;link&gt; 요소로 연결한 CSS 파일 안의 @import 문
5.  최종 사용자가 연결한 CSS 파일
6.  브라우저의 기본 스타일시트

예외적으로, 최종 사용자가 연결한 CSS 파일 안의  `!important`  규칙은 우선순위 1위다. 최종 사용자는 !important 규칙을 작성해서 웹사이트 디자이너가 만든 CSS 파일의 규칙을 무효화할 수 있다.

여러 CSS파일이 같은 우선순위 위치에서 연결되고 삽입되어 있을 때는 연결/삽입 순서에 따라 우선 순위가 결정된다. 가장 마지막에 연결/삽입된 스타일시트가 앞의 스타일시트보다 우선순위가 높다.

#### 우선순위 전략

우선순위를 최대한 단순하게 유지해야 한다는 것을 고려한다.

-   연결하는 CSS 파일의 수를 최소화
-   `@import`  문 사용을 자제
-   선택자를 각 CSS 파일 안에서의 의도한 순서대로 정렬
    
    CSS
    
    ```css
    @charset "utf-8";
    
    /* 전체 선택자 */
    * {
      -webkit-box-sizing: border-box;
      -moz-box-sizing:  border-box;
      box-sizing: border-box;
    }
    *:before, *:after {
      -webkit-box-sizing: border-box;
      -moz-box-sizing: border-box;
      box-sizing: border-box;
    }
    
    /* 요소 선택자 */
    html {
      font-family: sans-serif;
      -ms-text-size-adjust: 100%;
      -webkit-text-size-adjust: 100%;
    }
    article, aside, details, figcaption, figure, footer, header, hgroup, main, nav, section, summary {
      display:block;
    }
    
    /* 클래스 선택자, 속성 선택자, 가상 선택자 */
    .pull-left {
      float:left
    }
    .ab[title="abcd"] {
      position: absolute;
    }
    
    /* 아이디 선택자 */
    #content {
      position: relative;
    }
    
    /* !important 전체 선택자 */
    ...
    
    /* !important 요소 선택자 */
    ...
    
    /* !important 클래스 선택자, 속성 선택자, 가상 선택자 */
    ...
    
    /* !important 아이디 선택자 */
    ...
    
    ```
    

  
  
출처: [https://webdir.tistory.com/338](https://webdir.tistory.com/338) [WEBDIR]
