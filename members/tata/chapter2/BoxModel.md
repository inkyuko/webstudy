
HTML과 CSS를 완전히 이해하는데 필요한 하나의 원칙은 박스모델이다.

**“페이지의 모든 엘리먼트는 사각형 박스이다.”**

박스 모델을 이해하는 것은 어렵고 까다로울 수 있으나 일반적인 웹사이트를 만들기 위해서는 필요하다. 더불어 레이아웃을 만들기 위해, 페이지에 엘리먼트를 배치하는 방법을 아는 것도 똑같이 중요하다.

## 1. Box Sizing

이전의 강의를 통해 페이지에 모든 엘리먼트는, 블럭이나 인라인 레벨이건, 모두 사각형 박스라는 것을 알았을 것이다. 박스는 다른 크기를 가질 수 있으며, 마진, 패딩, 경계선 등이 크기를 변경할 수도 있다. 이것들을 통틀어  _the box model_이라 한다. 박스 모델의 한 예를 보자.

## 2. The Box Model

알다시피 모든 엘리먼트는 높이(height)와 너비(width)를 가지는 사각형 박스이며, 다른 마진(margin), 패딩(padding), 보더(boarder)로 구성되어 있다. 이 모든 값들이 합쳐져  [박스모델](http://css-tricks.com/the-css-box-model/)을 만든다.

박스는 엘리먼트의  `height`와  `width`의 속성값을 주는 것으로 시작된다.  `padding`과  `border`가 차례로  `height`  와  `width`를 둘러싼다. 그런 다음  `margin`이  `border`를 둘러싼다. 그러나, 마진은 박스의 실제 크기에는 포함되지 않으며, 박스모델을 정의하는 것에는 도움을 준다.

```
    div {
      background: #fff;
      border: 6px solid #ccc;
      height: 100px;
      margin: 20px;
      padding: 20px;
      width: 400px;
    }

```

박스모델에서 엘리먼트의 전체 너비는 다음 공식을 사용한다:

`margin-right`  +  `border-right`  +  `padding-right`  +  `width`  +  `padding-left`  +  `border-left`  +  `margin-left`

엘리먼트의 전체 높이 공식은

`margin-top`  +  `border-top`  +  `padding-top`  +  `height`  +  `padding-bottom`  +  `border-bottom`  +  `margin-bottom`


## 3. Height & Width

모든 엘리먼트는 상속된  `height`와  `width`를 갖는다. 어떤 엘리먼트가 페이지의 레이아웃과 디자인에 핵심요소(key)가 된다면 특정한  `height`와  `width`가 필요할 것이고 이때 블럭 레벨 엘리먼트의 디폴트 값은 (새로 지정된 값으로) 덮어씌워질 것이다.(overrided)


### 3.1. CSS Height Property

엘리먼트의  `height`의 디폴트 값은 컨텐츠에 의해 결정된다. 컨텐츠를 수용하기 위해 필요한 만큼 수직으로 늘어나거나 줄어들 것이다. 블럭 엘리먼트의 높이를 지정하기 위해는  `height`  속성이 사용된다.

```
div {
  height: 100px;
}

```

### 3.2. CSS Width Property

엘리먼트의  `width`의 디폴트값은 보여지는 방식에 달려있다. 블럭 레벨 엘리먼트는 width = 100% 가 디폴트이며, 가능한 모든 너비를 차지한다. inline 엘리먼트는 컨텐츠가 차지하는 만큼 수평적으로 늘어나고 줄어든다. 인라인 레벨 엘리먼트는 정해진 값을 가질 수 없으므로,  `height`  속성처럼  `width`  속성은 블럭 레벨 엘리먼트와만 관계가 있다.

```
div {
  width: 400px;
}

```

## 4. Margin & Padding

`margin`  과  `padding`은 브라우저마다 엘리먼트마다 가독성을 이유로 다른 디폴트 값을 가진다. 이러한 디폴트값을 모두 0로 맞추기 위해 [CSS reset](http://learn.shayhowe.com/html-css/terminology-syntax-intro#reset)을 사용하는 것을 논의했다.

### 4.1. CSS Margin Property

`margin`  속성으로 엘리먼트를 둘러싼 여백의 크기를 정할 수 있다. 마진은 경계선(border)의 바깥에 위치하며 완전히 투명하다. 마진으로 페이지의 특정 위치에 엘리먼트가 배치되는 것을 돕거나 다른 엘리먼트가 충분한 거리를 두도록 여백만을 줄 수도 있다.

```
div {
  margin: 20px;
}

```

### 4.2. CSS Padding Property

`padding`  속성은  `margin`  속성과 매우 유사하나 엘리먼트의 경계선(`border`)안에 위치한다. 패딩은 엘리먼트의 백그라운드를 상속한다.  `margin`  속성은 엘리먼트를 배치하기 위한 것이지만 패딩은 엘리먼트 안의 여백을 제공한다.

```
div {
  padding: 20px;
}

```

### 4.3. Margin & Padding Declarations(선언)

`margin`  과  `padding`  값은 롱핸드와 숏핸드 형식으로 줄 수 있다.

엘리먼트의 네 변을 하나의 값으로 설정하거나 상하, 좌우, 상우하좌로 한번에 설정할 수 있다.(숏핸드)

```
margin: 20px;             /* 상하좌우 모두 20px */
margin: 10px 20px;        /* 상하 10px, 좌우 20px */
margin: 10px 20px 0 15px; /* 상부터 시계 방향으로 상우하좌 순 */

```

한 개의 속성을 사용해서 한 번에 한 변의 값을 설정할 수 있다. 각 속성은  `margin`  혹은  `padding`으로 시작하며 -와 적용할  `top`,  `right`,  `bottom`, or  `left`  으로 적용할 변을 뒤따라 지정한다. 예를 들어  `padding-left`는 엘리먼트의 왼쪽 패딩에 값을 적용한다.(롱핸드)

```
div {
  margin-top: 10px;
  padding-left: 6px;
}

```

## 5. Borders(경계선)

경계선은  `padding`과  `margin`사이에 위치하며, 엘리먼트 주위의 아웃라인을 제공한다. 모든 경계선은 너비, 스타일, 색상의 세가지 값이 필요하다. 숏핸드 값은 너비, 스타일, 색상 순으로 주어진다. 롱핸드의 경우  `border-width`,  `border-style`,  `border-color`  값으로 나뉘어진다.

대부분 단순한 사이즈, 실선, 한가지 색의 경계를 볼 수 있을 것이다. 그러나  [수많은](http://www.quackit.com/html/codes/html_borders.cfm)  사이즈와 모양과 색상이 가능하다.

```
    div {
      border: 6px solid #ccc;
    }

```

> #### 5.1. Length Value
> 
> 마진, 패딩, 경계선과 쓸 수 있는  [길이 값](https://developer.mozilla.org/en/CSS/length)은 상대적인, 절대적인 값으로 여러 가지가 있다.
> 
> **상대 값**은 값이 적용되는 엘리먼트와 상관관계가 있다.  `em`과 퍼센티지 등이 있다.
> 
> **절대 값**은 엘리먼트와 상관없이 측정 단위로 고정된다. 픽셀, 포인트, 인치, 센티미터 등이 있다.
