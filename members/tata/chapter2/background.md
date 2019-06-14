
CSS background properties

- background-color
- background-image
- background-repeat
- background-attachment
- background-position

## background-color

-   **color값**  : 16진수의 컬러 값(#ffffff) 혹은 rgb 컬러 값(255,255,255), 키워드(white)
-   **transparent**  : 기본값으로 투명이다.
-   **inherit**  : 부모 요소로부터 값을 상속 받는다.
  

## background-image

-   박스 배경은 여러 개의 레이어(멀티 배경)를 가질 수 있다.
-   background-image 속성에 콤마로 구분하여 여러 개의 레이어를 지정할 수 있다.
-   none 값을 포함한 모든 값은 하나의 레이어를 의미한다.
-   각 이미지 레이어는 크기 및 위치를 조정할 수 있으며, 각 배경의 속성 값에 따라 반복적으로 나타날 수 있다.
-   첫 번째로 지정한 이미지가 사용자에게 가깝게 보여진다.


## background-repeat

-   **repeat**  : 배경이 수평 및 수직 방향으로 반복된다.
-   **repeat-x**  : 배경이 수평 방향으로만 반복된다.
-   **repeat-y**  : 배경이 수직 방향으로만 반복된다.
-   **no-repeat**  : 배경이 반복되지 않는다.
-   **round**  : 배경 영역을 채우기 위해 필요한 만큼만 반복된다. 이미지의 반복으로 배경 영역을 채우지 못하면 이미지의 크기가 조정된다.
-   **space**  : 이미지 클리핑 없이 배경의 위치 영역을 채우기 위해 필요한 만큼만 반복되며, 영역을 채우기 위해 이미지 사이의 공간이 벌어진다. 첫 번째와 마지막 이미지는 영역의 가장자리에 나타난다.
-   **inherit**  : 부모 요소로부터 값을 상속 받는다.


### background-attachment

-   **scroll**  : 배경이 요소에 고정되어 문서와 함께 스크롤된다. 이 값이 기본값이다.
-   **fixed**  : 뷰 포트에 따라 고정된다.
-   **local** : 요소의 콘텐츠 위치를 상속받아 콘텐츠와 함께 스크롤된다.
  
  
### background-position

-   키워드를 하나만 지정하면 두 번째 값은 center가 된다.
-   기본값은 왼쪽 상단, 즉 0 0 이다. 퍼센트 값을 이용하거나 혹은 top left 키워드를 이용할 수 있다.
-   퍼센트 값과 위치 값은 혼합해서 사용할 수 있다.
-   퍼센트 값은 배경의 위치 영역의 크기에서 배경 이미지의 크기를 뺀 값을 의미한다.

-   **left top / left center / left bottom / right top / right center / right bottom / center top / center center / center bottom** : 키워드 속성값이고 하나만 지정하면 두 번째 값은 center가 된다.
-   **x% y%**  : 퍼센트 부호(%)가 뒤에 오는 정수를 지정한다.
-   **xpos ypos**  : px를 포함해서 in, cm, mm, em, ex, pt, pc등을 사용할 수 있다.
-   **inherit**  : 부모 요소로부터 값을 상속 받는다.
  
### background-size

-   **width height**  : 첫 번째 값은 width 값이며, 두 번째 값은 height 값이다. width와 height 속성에 사용할 수 있는 값은 auto, px, % 이다. 두 번째 값을 생략하면 auto 값이 적용된다.
-   **cover**  : 가능한한 배경 이미지 배율을 크게 하여 배경 이미지를 배경 영역에 포함시킨다. 배경 이미지의 일부분은 배경 위치 영역을 벗어날 수 있다.
-   **contain**  : content 영역 안쪽에 width와 height 둘다 가능한한 가장 큰 사이즈로 배경 이미지 크기를 조정한다.
   
