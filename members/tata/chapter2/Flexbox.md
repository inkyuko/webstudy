
# Flexbox

- 복잡한 계산 없이 요소의 크기와 순서를 유연하게 배치할 수 있는 레이아웃 방식

## 구성

- 복수의 자식 요소인 flex item과 그 상위 부모 요소인 flex container로 구성  

![flexcontainer](https://d2.naver.com/content/images/2018/12/helloworld-201811-flex_01.png)

~~~css
.flex_container {
	display:flex;
}
~~~

## 부모 요소와 자식 요소에 정의하는 속성 구분

### flex container
- flex-direction
- justify-content
- align-items
- flex-wrap
- align-content  

### flex item
- flex
- flex-grow
- flex-shrink
- flex-basis
- order


![flexproperty](https://d2.naver.com/content/images/2018/12/helloworld-201811-flex_02.png)

### align-items
- 수직 방향 정렬 방식을 제공
~~~css
.flex_container {
	align-items : center;
}
~~~

### flex-direction
- 주축의 방향은 왼쪽에서 오른쪽으로 향하는 수평 방향
- row (default)
- column
~~~css
.flex_container { 
	display: flex; 
	flex-direction: column; 
} 
.flex_item { 
	flex: 1; /* flex: 1 1 0 */  
}
~~~

### flex
- item의 크기와 관련된 속성

~~~css
.flex_item { 
	flex:1;
}
.flex_item { 
	flex:1 1 0;
}
.flex_item {
	flex-grow: 1; 
	flex-shrink: 1; 
	flex-basis: 0;
}
~~~

### flex-grow
- item의 확장에 관련된 속성
- 0과 양의 정수를 값에 사용
- 속성값이 0이면 container의 크기가 커져도 item의 크기는 유지
- container의 크기에 따라 유동적으로 크기를 유지하려면 1이상의 값의 사용

### flex-shrink
- item의 축소에 관련된 속성
- 0과 양의 정수를 값에 사용
- 기본값은 1
- 속성값이 0이면 container의 크기가 item의 크기보다 작아져도 item의 크기는 유지
- 속성값이 1 이상이면 container의 크기가 item의 크기보다 작아질 때 container의 크기에 맞춰 작아짐

### flex-basis
- item의 기본 크기를 결정하는 속성
- 기본값은 auto
- width 속성에서 사용하는 모든 단위(px,%,em,rem)를 사용 가능

## browser support


![support](https://d2.naver.com/content/images/2018/12/helloworld-201811-flex_03.png)

- IE 10 이상 지원하지만 완전히 지원 하지 않음
