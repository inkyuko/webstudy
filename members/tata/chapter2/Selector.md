## 1. CSS 선택자(Selector)란?

선택자란 말 그대로 선택을 해주는 요소입니다. 이를 통해 특정 요소들을 선택하여 스타일을 적용할 수 있게 됩니다. 먼저 CSS에서 스타일이 어떤 방식으로 정의되는지 알아봅시다.

### 1.1 Rule Set

Rule Set(Rule)은 HTML페이지 안의 특정 요소들을 어떻게 렌더링(Rendering) 할 것인지 브라우저에게 알려주는 CSS 문장입니다. 스타일 규칙이라고도 불리는 이 문장은 스타일에 관한 규칙들을 집합처럼 나타냅니다.

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140327-selector-04.png)

[그림 1] Rule Set

이런 문장들을 한군데에 모으면 스타일 시트(Style Sheet)를 이루게 되어, 많은 수의 스타일 규칙들을 관리하기 쉬워집니다.

1.2 선택자(Selector)

위쪽 [그림 1]을 다시 보시면, Rule Set 제일 앞 부분의 선택자 요소를 볼 수 있는데요. 왼쪽 중괄호 "{"가 나오기 전의 부분 모두가 선택자입니다. 선택자는 Rule Set의 영향을 받는 HTML페이지 안의 특정 element들을 선택해서 선언 블록(Declaration Block)의 내용을 적용시켜 줍니다.

참고)  
@media print { background-color: transparent; } “@”키워드로 시작하는 문장은 Rule Set이 아닌 At-Rule이기 때문에 위 문장에서의 중괄호 전 부분은 선택자가 아닙니다.

## 2. 선택자(Selector)의 종류

디자인 요소를 의도에 알맞게 적용하기 위해서는 많은 종류의 선택자를 잘 혼합해서 사용하는 것이 중요합니다. 그 종류와 CSS 레벨, 지원하지 않는 브라우저 버전을 함께 알아봅니다.

### 2.1 전체 선택자(Universal Selector)
<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>*</td>  
<td>HTML페이지 내부의 모든 태그를 선택합니다.</td>  
<td>2</td>  
<td>-</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
* { margin: 0; text-decoration: none; }

```

_[예제 1] 전체 선택자_

전체 선택자는 HTML페이지 내부의 모든 요소(태그)에 같은 CSS속성을 적용합니다. 그렇기 때문에 보통 [예제 1]처럼 margin이나 padding값을 초기화하는 등 기본값을 정해둘 때 사용합니다. 하지만 이를 사용하면 문서안의 모든 요소를 읽어내려야 하기 때문에 페이지 로딩의 속도가 느려질 수 있습니다. 따라서 자주 사용하지 않는 것이 좋습니다.

### 2.2 태그 선택자(Type Selector)
<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E</td>  
<td>태그명이 E인 특정 태그를 선택합니다.</td>  
<td>2</td>  
<td>-</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
p { background: yellowgreen; color: darkgreen; }

<!-- HTML -->  
<p>태그 선택자(Type Selector)</p>  
<div>태그 선택자(Type Selector)</div>  

```

_[예제 2] 태그 선택자_

태그 선택자는 HTML요소를 직접 지칭하는 가장 간단한 선택자입니다. [예제 2]를 보시면 CSS에서

태그에 대한 스타일만 지정이 되어있으므로,

태그에는 개발자가 지정해주는 스타일이 적용되지 않습니다.

### 2.3 클래스 선택자(Class Selector)
<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>.myClass</td>  
<td>클래스 속성값이 myClass으로 지정된 요소를 선택합니다.</td>  
<td>1</td>  
<td>-</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
.class1 { background: yellowgreen; color: darkgreen; }
div.class2 { background: darkgreen; color: yellowgreen; }

<!-- HTML -->  
<p class="class1">클래스 선택자(Class Selector)</p>  
<p class="class2">클래스 선택자(Class Selector)</p>  
<div class="class2">클래스 선택자(Class Selector)</div>  

```

_[예제 3] 클래스 선택자_

클래스 선택자는 주어진 값을 class속성값으로 가진 HTML요소를 찾아 선택합니다. 이때 선택하려는 속성값 앞에 마침표를 추가해서 작성합니다. [예제 3] CSS 코드의 첫번째 스타일 규칙은 class1이라는 class 속성값을 가진 모든 태그를 선택합니다. 하지만 두번째 스타일 규칙처럼 마침표 앞에 태그를 붙여주면 범위를 그 특정 태그에 한합니다. 결국 HTML 코드의 두번째

태그 부분은 class 속성값이 class2임에도 선택되지 않습니다.

**클래스 선택자를 사용하기 전에 생각해야 할 부분**

1.  class요소 대신 사용할 수 있는 HTML 태그가 있는지 확인합니다.  
    한가지 예를 들어보겠습니다. heading처리한 글씨처럼 보이기 위하여  `<h1>`과 같은 태그 대신 class선택자를 사용하여 스타일 속성을 줄 수 있습니다. 하지만 이렇게 사용하면 스타일 시트를 적용하지 못하는 (극히 일부일지라도) 브라우저에서는 제목의 기능을 하지 못할 수 있습니다. 그래서, 가능한 올바른 HTML요소를 사용하고 스타일은 따로 적용해야 합니다. 결국 클래스는 HTML태그. 즉 구조를 대신할 수 없습니다.
    
2.  DOM트리 상단에 사용되는 클래스나 ID가 있는지 확인합니다.  
    불필요하게 많은 class선택자를 사용할 필요는 없습니다. DOM트리 상단에 같은 스타일을 공유하는 클래스나 ID가 있다면, 새로 클래스 선택자를 사용할 필요없이 함께 사용하면 됩니다.
    

### 2.4 ID 선택자(ID Selector)
<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>#myId</td>  
<td>id 속성값이 myId로 지정된 요소를 선택합니다.</td>  
<td>1</td>  
<td>-</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
#id1 { background: yellowgreen; color: darkgreen; }
div#id2 { background: darkgreen; color: yellowgreen; }

<!-- HTML -->  
<p id="id1">ID 선택자(ID Selector)</p>  
<p id="id2">ID 선택자(ID Selector)</p>  
<div id="id2">ID 선택자(ID Selector)</div>  

```

_[예제 4] ID 선택자_

ID선택자는 마침표 대신 #를 사용하고, class속성이 아닌 id속성을 사용하는 것을 제외하곤 클래스 선택자와 매우 유사합니다. 따라서 [예제4] 역시 [예제3]과 같은 결과가 나옵니다. 하지만 이 둘 사이엔 어떤 문자를 사용하느냐보다 더 중요한 차이점이 있습니다.

**클래스 선택자를 써야 할까요? ID선택자를 써야 할까요?**

비슷하게 사용되는 두 선택자 중 어떤 것을 사용해야 할지 고민에 빠지는 경우가 생길 수 있습니다. 그럴땐 다음 네 가지를 고려해보면 됩니다.

1.  한 페이지 내에서 여러 번 반복될 필요가 있는 스타일은 클래스 선택자를 사용하고, 단 한번 유일하게 적용될 스타일은 ID선택자를 사용하는 것이 좋습니다. 이는 다음과 같은 두 속성의 차이 때문입니다.
    
    -   class속성은 어떤 분류 안에 포함된 요소의 특성을 정의하는 데 사용됩니다.
    -   id속성은 어떤 요소에 대해 유일한 특성을 정의합니다. (HTML 문서에서 특정 id속성값은 오직 하나만 있어야 합니다.)
2.  클래스 선택자는 글자색이나 글자 굵기 등 나중에 다른 곳에도 적용할 수 있는 스타일을 지정하고, ID선택자는 웹 문서 안에서 요소의 배치 방법을 지정할 때 자주 사용합니다.
    
3.  class 속성은 속성값을 두 개 이상 가질 수 있습니다. 그래서 클래스 선택자를 사용하면 한 태그 내에서도 여러종류의 스타일 규칙을 적용할 수 있습니다.
    
4.  ID선택자의 우선순위가 클래스 선택자의 우선순위보다 높습니다. 우선으로 적용되어야 할 스타일을 ID선택자를 사용하여 정의하는 것이 좋습니다. (선택자 우선순위는 뒤에서 다시 언급합니다.)
    

### 2.5 복합 선택자(Combinator)

복합 선택자는 두 개 이상의 선택자 요소가 모인 선택자입니다. (이는 꼭 태그 선택자 간의 결합이 아니어도 됩니다.)

**하위 선택자(Descendant Combinator)와 자식 선택자(Child Combinator)**

<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E F</td>  
<td>E 요소의 자손인 F 요소를 선택합니다.</td>  
<td>1</td>  
<td>-</td>  
</tr>  
<tr>  
<td>E&gt;F</td>  
<td>E 요소의 자식인 F 요소를 선택합니다.</td>  
<td>2</td>  
<td>IE6</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
/* 하위 선택자 */
section ul { border: 1px dotted black; }

/* 자식 선택자 */
section>ul { border: 1px dotted black; }  

```

_[예제 5] 하위 선택자와 자식 선택자_

태그들이 포함 관계를 가질 때 포함하는 요소를 부모 요소, 포함되는 요소를 자식 요소라고 합니다. 하위 선택자는 부모 요소에 포함된 '모든' 하위 요소에 스타일을 적용합니다. 하지만, 자식 선택자는 부모의 바로 아래 자식 요소에만 적용합니다. [예제 5]를 통해 선택되는 요소는 다음과 같습니다.

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140331-selector-06.png)

[그림 2] 하위 선택자

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140331-selector-06-2.png)

[그림 3] 자식 선택자

_인접 형제 선택자(Adjacent Sibling Combinator)와 일반 형제 선택자(General Sibling Combinator)_


<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E+F</td>  
<td>  
E 요소를 뒤따르는 F 요소를 선택합니다.<br>  
(E와 F 사이에 다른 요소가 존재하면 선택하지 않습니다.)
</td>  
<td>2</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E~F</td>  
<td>  
E 요소가 앞에 존재하면 F를 선택합니다.<br>  
(E가 F보다 먼저 등장하지 않으면 선택하지 않습니다.)
</td>  
<td>3</td>  
<td>IE6</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
/* 인접 형제 선택자 */
h1+ul { background: yellowgreen; color: darkgreen; }

/* 일반 형제 선택자 */
h1~ul { background: darkgreen; color: yellowgreen; }  

```

_[예제 6] 인접 형제 선택자와 일반 형제 선택자_

같은 부모 요소를 가지는 요소들을 형제 관계라고 부릅니다. 이 때 먼저 나오는 요소를 '형 요소', 나중에 나오는 요소를 '동생 요소'라고 합니다. 먼저 나온다는 것은 html문서에 먼저 쓰여지는 것을 말합니다.

인접 형제 선택자는 형제 중 첫번째 동생 요소가 조건을 충족시킬 때에만 스타일을 적용합니다. 하지만 일반 형제 선택자는 조건을 충족하는 모든 동생 요소에 스타일을 적용합니다. 두 선택자 모두 형 요소에는 적용되지 않습니다. [예제 6]을 통해 선택되는 요소는 다음과 같습니다.

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140331-selector-07.png)

[그림 4] 인접 형제 선택자

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140331-selector-08.png)

[그림 5] 일반 형제 선택자

### 2.6 속성 선택자(Attribute Selectors)

위에서 살펴본 선택자들은 태그나 클래스 이름, ID이름만 알면 그대로 스타일을 적용할 수 있습니다. 하지만 이제 살펴볼 속성 선택자는 클래스 속성이나 ID속성과 같이 대표적인 속성이 아닌 태그 안의 특정 속성들에 따라 스타일을 지정합니다. 속성 값의 조건에 따라 다양한 스타일을 지정할 수 있기 때문에 활용도가 높은 스타일 지정 방식입니다.

<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E[attr]</td>  
<td>'attr' 속성이 포함된 요소 E를 선택합니다.</td>  
<td>2</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E[attr="val"]</td>  
<td>'attr' 속성의 값이 정확하게 'val'과 일치하는 요소 E를 선택합니다.</td>  
<td>2</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E[attr~="val"]</td>  
<td>  
'attr' 속성의 값에 'val'이 포함되는 요소를 선택합니다.<br>  
(공백으로 분리된 값이 일치해야 합니다.)
</td>  
<td>2</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E[attr^="val"]</td>  
<td>'attr' 속성의 값이 'val'으로 시작하는 요소를 선택합니다.</td>  
<td>3</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E[attr$="val"]</td>  
<td>'attr' 속성의 값이 'val'으로 끝나는 요소를 선택합니다.</td>  
<td>3</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E[attr*="val"]</td>  
<td>'attr' 속성의 값에 'val'이 포함되는 요소를 선택합니다.</td>  
<td>3</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E[attr|="val"]</td>  
<td>  
'attr' 속성의 값이 정확하게 'val' 이거나<br>  
'val-' 으로 시작되는 요소 E를 선택합니다.  
</td>  
<td>2</td>  
<td>IE6</td>  
</tr>  
</tbody>  
</table>

```
/* CSS */
/* E[attr]형식 */
a[href] { background: yellowgreen; color: black; }

/* E[attr="val"]형식 */
input[type="text"] { width: 150px; border: 1px solid #000; }

/* E[attr$="val"]형식 */
a[href$=".xls"] { background: darkgreen; }

<!-- HTML -->  
<a href="one.html">E[attr]형식</a>  
<input type="text" name="name">  
<a href="one.xls">E[attr$="val"]형식</a>  

```

_[예제 7] 속성 선택자_

속성 선택자는 모두 앞쪽에 태그명과 대괄호 "[]"사이에 속성에 관련된 내용을 넣어서 선택합니다. E[attr="val"]형식은 속성과 속성값이 완벽하게 일치하는 경우에 선택됩니다. 하지만 E[attr~="val"]선택자는 띄어쓰기를 통해 여러개 올 수 있는 속성값 중 하나만 일치해도 선택합니다.

또한 E[attr^="val"]형식은 "val"으로 시작하는 속성값을 선택합니다. 예를 들어 웹 문서에서 외부로 연결되는 링크가 있을 경우  [http://로](http://xn--2o2b/)  시작하는지 확인하기 위해 이 선택자를 쓸 수 있습니다. 반대로 E[attr$="val"]형식은 "val"으로 끝나는 속성값을 선택합니다. 이 선택자는 예제6에 나온 것 처럼 어떤 파일이 링크될 경우, 그 파일의 확장자를 확인하기 위해 쓸 수 있습니다.

### 2.7 가상 클래스 선택자(Pseudo-Classes)

가상 클래스는 웹 문서의 소스에는 실제로 존재하지 않지만 필요에 의해 임의로 가상의 선택자를 지정하여 사용하는 것을 말합니다.

**링크 선택자(The link pseudo-classes)와 동적 선택자(The user action pseudo-classes)**


<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::link</td>  
<td>방문하지 않은 링크 E를 선택합니다.</td>  
<td>1</td>  
<td>-</td>  
</tr>  
<tr>  
<td>E::visited</td>  
<td>방문한 링크 E를 선택합니다.</td>  
<td>1</td>  
<td>-</td>  
</tr>  
<tr>  
<td>E::active</td>  
<td>E 요소에 마우스 클릭 또는 키보드 엔터가 눌린 동안 E를 선택합니다.</td>  
<td>1, 2</td>  
<td>-</td>  
</tr>  
<tr>  
<td>E::hover</td>  
<td> E 요소에 마우스가 올라가 있는 동안 E를 선택합니다.</td>  
<td>1, 2</td>  
<td>-</td>  
</tr>  
<tr>  
<td>E::focus</td>  
<td>E 요소에 포커스가 머물러 있는 동안 E를 선택합니다.</td>  
<td>1, 2</td>  
<td>-</td>  
</tr>  
</tbody>  
</table>

:link와 :visited는 문서 안의 링크와 관련된 선택자입니다. 나머지 세가지 선택자는 링크 요소뿐만 아니라 다른 요소에도 적용할 수 있습니다. :active선택자는 해당 요소가 활성화된 상태를 선택합니다. 링크요소가 선택된 경우를 예로 들 수 있습니다. :hover선택자는 마우스 포인터가 해당 요소위에 올라가 있는 상태를 선택합니다. 흔히 말하는 롤오버 효과(rollover)를 만드는 선택자입니다. 마지막 :focus선택자는 해당 요소에 초점이 맞춰있는 상태를 선택합니다. 초점이 맞춰졌다는 것은 텍스트 필드 안에 커서가 놓여진 것과 같은 상태를 말합니다.

**구조적 가상 클래스 선택자(Structural pseudo-classes)**

구조적 가상 클래스 선택자는 위치를 기준으로 삼습니다. 그래서 요소가 몇번째에 있느냐에 따라 스타일을 다르게 지정할 수 있게 해줍니다. 순차적으로 같은 태그의 여러 항목이 있을 경우, 메뉴 간의 스타일을 변경하거나 할 때 이 선택자들이 유용하게 쓰입니다.

<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::root</td>  
<td>문서의 최상위 요소(html)를 선택합니다.</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::nth-child(n)</td>  
<td>앞으로부터 지정된 순서와 일치하는 요소가 E 라면 선택합니다.<br>  
(E 아닌 요소의 순서가 계산에 포함)    </td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::nth-last-child(n)</td>  
<td>뒤로부터 지정된 순서와 일치하는 요소가 E 라면 선택합니다.<br>  
(E 아닌 요소의 순서가 계산에 포함)</td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::nth-of-type(n)</td>  
<td>E 요소 중 앞으로부터 순서가 일치하는 E 요소를 선택합니다.<br>  
(E 요소의 순서만 계산에 포함)</td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::nth-last-of-type(n)</td>  
<td>E 요소 중 끝으로부터 순서가 일치하는 E 요소를 선택합니다.<br>  
(E 요소의 순서만 계산에 포함)</td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::first-child</td>  
<td>첫 번째 등장하는 요소가 E 라면 선택합니다.<br>  
(E 아닌 요소의 순서가 계산에 포함)</td>
<td>2</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E::last-child</td>  
<td>마지막에 등장하는 요소가 E 라면 선택합니다.<br>  
(E 아닌 요소의 순서가 계산에 포함)    </td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::first-of-type</td>  
<td>E 요소 중 첫 번째 E를 선택합니다.(E 요소의 순서만 계산에 포함)</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::last-of-type</td>  
<td>E 요소 중 마지막 E를 선택합니다.(E 요소의 순서만 계산에 포함)</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::only-child</td>  
<td>E 요소가 유일한 자식이면 선택합니다.<br>  
(E 아닌 요소가 하나라도 포함되면 선택하지 않습니다.)</td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::only-of-type</td>  
<td>E 요소가 유일한 타입이면 선택합니다.<br>  
(E 아닌 요소가 포함되어도 E 타입이 유일하면 선택합니다.)</td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::empty</td>  
<td>텍스트 및 공백을 포함하여 자식 요소가 없는 E를 선택합니다.</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
</tbody>  
</table>

**그 외의 선택자**

_언어 선택자(language pseudo-classes)_

<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::lang(ko)</td>  
<td>HTML lang 속성의 값이 'ko'으로 지정된 요소를 선택합니다.</td>  
<td>2</td>  
<td>IE6, 7</td>  
</tr>  
</tbody>  
</table>

_부정 선택자(Negation pseudo-class)_

<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::not(S)</td>  
<td>S가 아닌 E 요소를 선택합니다.</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
</tbody>  
</table>

_목적 선택자(The target pseudo-class)_


<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::target</td>  
<td>E의 URI가 요청되면 선택합니다.<br>  
(따라서 E는 ID가 지정되어 있어야 합니다.)</td>
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
</tbody>  
</table>

_UI요소 상태 선택자(The UI element states pseudo-classes)_


<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::enabled</td>  
<td>사용 가능한 폼 콘트롤(input, textarea, select, button) E를 선택합니다.</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::disabled</td>  
<td>사용 불가능한 폼 콘트롤(input, textarea, select, button) E를 선택합니다.</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
<tr>  
<td>E::checked</td>  
<td>선택된 폼 콘트롤(input checked="checked")을 선택합니다.</td>  
<td>3</td>  
<td>IE6, 7, 8</td>  
</tr>  
</tbody>  
</table>

_가상 엘리먼트 선택자(Pseudo-Elements)_


<table border="1">  
<colgroup><col width="20%">  
<col width="55%">  
<col width="10%">  
<col width="15%">  
</colgroup><thead>  
<tr>  
<th>패턴</th>  
<th>의미</th>  
<th>CSS Level</th>  
<th>지원하지 않는<br>브라우저</th>  
</tr>  
</thead>  
<tbody>  
<tr>  
<td>E::first-line</td>  
<td>E 요소의 첫 번째 라인을 선택합니다.</td>  
<td>1</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E::first-letter</td>  
<td>E 요소의 첫 번째 문자를 선택합니다.</td>  
<td>1</td>  
<td>IE6</td>  
</tr>  
<tr>  
<td>E::before</td>  
<td>E 요소의 시작 지점에 생성된 요소를 선택합니다.</td>  
<td>2</td>  
<td>IE6, 7</td>  
</tr>  
<tr>  
<td>E::after</td>  
<td>E 요소의 끝 지점에 생성된 요소를 선택합니다.</td>  
<td>2</td>  
<td>IE6, 7</td>  
</tr>  
</tbody>  
</table>

## 3. 선택자(Selector) 우선순위

스타일 시트는 다음과 같은 3개의 CSS원천 소스(Original Source)를 가질 수 있습니다.

-   제작자(author) 원천 소스 : 웹 사이트 제작자가 지정하는 자신의 페이지 스타일
-   사용자(user) 원천 소스 : 사용자가 직접 정하는 자신이 사용할 스타일
-   사용자 도구(user agent) 원천 소스 : 웹 브라우저 자체에 지정된 기본 스타일

스타일을 적용하는데는 다양한 방법이 있으며 동시에 여러가지 방법을 사용하게 되면 스타일이 충돌할 수 있습니다. 그렇기 때문에 각 원천 소스간은 물론, 선택자 간의 우선순위를 알아야 합니다. 다음의 우선순위 규칙을 통해 원하는 스타일을 정확히 적용할 수 있습니다.

### 1) 원천 소스 우선 순위

!important 선언을 한 사용자 스타일 > !important 선언을 한 제작자 스타일 > 제작자 스타일 > 사용자 스타일 > 사용자 도구 선언 (브라우저 자체의 선언)

### 2) CSS 명시도(Specificity) 계산법

```
!important > id [ 100 ] > class [ 10 ] > tag [ 1 ] > * [ 0 ]

```

!important선언을 사용한 형식이 가장 우선 순위가 높습니다. 그래서 다른 선언들을 덮어버릴 수 있기 때문에 꼭 필요한 곳에만 사용해야 합니다.

이를 제외한 나머지 선택자는 대괄호 "[]"안에 있는 숫자를 각각의 점수로 부여하여 우선순위를 계산합니다.

-   ID 선택자의 갯수를 세어서 개당 100 으로 계산합니다. (= a)
-   클래스 선택자의 갯수를 세어서 개당 10 으로 계산합니다. (= b)
-   태그 선택자의 갯수를 세어서 개당 1 로 계산합니다. (= c)
-   공용 선택자는 모두 0으로 계산합니다. (= d)
-   가상 엘리먼트는 무시합니다.

→ a + b + c + d의 값이 높은 순서대로 스타일을 적용하는 우선순위를 가지게 됩니다. 다음의 예를 봅시다.

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140331-selector-09--1-.png)

초록색으로 표시된 태그 선택자 3개와 빨간색으로 표시된 클래스 선택자 1개로 이루어진 스타일 규칙입니다. 우선순위 규칙에 따라 b의 값은 10×1=10이 되고, c의 값은 1×3=3이 됩니다. 따라서 이 스타일 규칙의 우선순위 값은 13입니다.

![](http://www.nextree.co.kr/content/images/2016/09/yrkim-140331-selector-11.png)

초록색으로 표시된 태그 선택자 1개와 파란색으로 표시된 ID 선택자 1개로 이루어진 스타일 규칙입니다. 우선순위 규칙에 따라 a의 값이 100×1=100이 되고, c의 값은 1×1=1이 됩니다. 따라서 이 스타일 규칙의 우선순위 값은 101입니다.

이 두 스타일 규칙이 하나의 html태그에 겹치는 가능한 다음과 같은 경우가 있다고 하면, 우선순위 값이 101인 아래쪽의 스타일 규칙이 적용됩니다.

```
<ul>  
....
</ul>  
<ol>  
    <li class="num" id="selector1"></li>  /* 아래쪽 스타일 규칙이 적용되는 부분 */
</ol>  

```

### 3) 마지막에 지정된 스타일을 우선 적용합니다.

스타일 우선순위가 같거나, 계산 방법이 없는 경우 마지막에 지정된 스타일이 우선으로 적용됩니다. 예를 들어 자손 선택자와 자식 선택자가 부딪힐 경우, 우선순위 계산법이 없으므로 두 선택자 중 마지막에 지정된 스타일이 적용됩니다.
