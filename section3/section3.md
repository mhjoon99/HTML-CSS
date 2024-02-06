## 섹션3. 간단한 버튼을 만들면서 HTML CSS 배우기

### 가상 클래스(의사 클래스)

#### first-child와 first-of-type 비교

```html
<style>

        .parent p:first-child {

            color: lightpink;

        }

.parent p:first-of-type {

            color: lightpink;

        }

    </style>

<div class="parent">

        <span>A</span>

        <p>B</p>

        <p>C</p>

    </div>
```

- First-child :  <div class=“parent”의 두 번째 자식 => 그래서 처음 자식이 아니라 적용 x

- First-of-type : <p> 라는 타입이 처음 등장 => 그래서 <p> 타입의 처음 자식이기에 적용 o

### 가상 요소 (의사 요소)

- ::before와 ::after는 꼭 ‘content’와 같이 쓰여야 하며, 이 content는 ‘가짜’ 속성

- HTML 문서에 정보로 포함되지 않은 요소를 CSS에서 새롭게 생성해주는 역할

### Float CSS

- 레이아웃을 만들 때 사용 가능, 요즘에는 float 대신 훨씬 강력한 도구 flexbox 및 grid 사용


### Clear CSS
- Clear CSS를 이용해서 float의 영향을 받지 않도록 할 수 있음
- Float 속성을 사용하고 아래에 다음 요소를 원할 때 clear 속성 사용

### CSS Box Model (Margin, Padding, Border)
- Margin : 테두리 밖의 영역을 지운다. margin은 투명
- Padding: 콘텐츠 주변 영역을 지운다. padding은 투명
- Border : 패딩과 콘텐츠를 둘러싸는 테두리

> margin과 padding의 차이점: margin은 음수가 영향이 있지만, padding은 음수가 영향이 없다.

### Image, Input 요소
1. Image
	- src : 태그의 src 속성은 이미지 소스의 URL 명시
	- alt : 태그의 alt 속성은 이미지를 보여줄 수 없을 때 이미지를 대체할 텍스트 명시


## 섹션4. Flexbox, Grid, Display

### Flexbox
- **flexbox는 많이 쓰이기 때문에 매우 중요!**
- 반응형 레이아웃을 만들 때 쓰는 모델
- 1차원 레이아웃
- 컨테이너 안에 있는 아이템들을 효율적으로 정렬하기 위해 css3에서 도입

- 구성요소 : flex container, flex items


### Flex Container
- Flex container : flex / inlinfe-flex로 상위 요소의 속성 정의
		ex) display:flex / display:inline-flex
- Flex container properties
    - Flex-direction : 주축, 교차축을 참조하여 작동
        - 종류 : row | row-reverse | column | column-reverse
            - Row 가로축이 주축 / column 세로축이 주축
    - Flex-wrap : flex의 디폴트 설정이라면, 아이템의 크기가 줄어들며 어떻게든 단일한 줄에 포함시킬 것. 그러나, flex-wrap 설정을 해주면 줄 바꿈이 일어남
        - 종류 : nowrap | wrap | wrap-reverse
            - Nowrap(기본값) : 모든 플렉스 항목이 한 줄에 표시
            - Wrap : 플렉스 항목은 위에서 아래로 여러 줄로 줄바꿈
            - wrap-reverse: 플렉스 항목은 아래에서 위로 여러 줄로 줄바꿈
    - Flex-flow : flex-direction 및 flex-wrap 속성의 약어로, 함께 플렉스 컨테이너의 기본 축과 교차 축을 정의. 기본값 : row nowrap
    - Justify-content : 주축을 따라 정렬을 정의. 항목이 유연하지 않거나 유연하지만 최대 크기에 도달한 경우 남은 여유 공간을 분산하는 데 도움. Items이 줄을 넘을 때 항목의 정렬 제어.
        - 종류 : flex-start | flex-end | center | space-between | space-around | space-evenly
    - Align-items : 축의 수직 방향을 기준으로 정렬. 현재 줄의 cross axis를 따라 플렉스 item이 배치되는 방식. Justify-content의 교차축 버전으로 이해하면 편함.
        - 종류 : flex-start | flex-end | center | stretch | baseline
    - Align-content : align-items는 한 줄을 정렬하는 반면, align-content는 두 줄부터 상요하는 데 의미가 있음. 따라서, 두 줄의 flex-wrap:wrap인 상태에서 사용해야 함.
        - 종류 : flex-start | flex-end | center | stretch | space-between | space-around
    - Align-self : 개별 플렉스 항목에 대해 정렬을 재정의 가능. 부모 요소의 자식 아이템들을 각각 다른 방식으로 정렬하고 싶을 때 사용. 단, align-content 속성이 없어야 작동.

### flex items
- Flex items : 플렉스 컨테이너의 직계 자식
- Flex items properties
    - order : 기본적으로 flex items는 소스 코드에 나열된 순서대로 배치. 그러나. order 속성은 플렉스 컨테이너에 나타나는 순서를 제어. 기본값 : 0
    - Flex-grow / Flex-shrink : 플렉스 박스 아이템의 기본 너비를 자동으로 늘이거나(flex-grow) 줄어들도록(flex-shrink)해서 행 안에 적절한 너비로 배치되도록 맞추는 기능. Item이 컨테이너 박스 내부의 사용 가능한 공간의 양을 나타냄. 비율로 사용되는 단위 없는 값 사용하고, 음수는 허용되지 않음. 
        - Flex-grow -> 기본 값 : 0 	flex-shrink -> 기본 값 : 1
        - Flex-shrink 속성은 플렉스 박스에 flex-wrap: wrap 속성을 부여한 경우 적용 x.
    - Flex-basis : 나머지 공간이 분배되기 전에 요소의 크기를 정의.
        - Flex 아이템의 기본 사이즈를 지정하는 속성. 
        - 기본값 : auto
        - width에서 사용하는 모든 단위(px, %, em, rem 등) 사용 가능
    - Flex : flex-grow, flex-shrink, flex-basis가 결합된 약어.
        - 두번째, 세번째 매개변수(flex-shrink / flex-basis)는 선택 사항. 필수 x.
        - 기본값 : 0 1 auto
        - 매개 변수에 따라…
			1. 값이 한 개일 때
				- 단위 x -> flex-grow
				-  단위 o -> flex-basis
			2. 값이 두 개일 때
				- 첫 번째 값 : flex-grow (단위 없어야 함)
				- 두 번째 값 : 단위 x->flex-shrink | 단위 o or auto -> flex-basis
			3. 값이 세 개 일 때
				- 첫 번째 값 : flex-grow (단위 없어야 함)
				- 두 번째 값 : flex-shrink (단위 없어야 함)
				- 세 번째 값 : flex-basis (단위 있거나 auto여야 함)


### Grid CSS
- Grid CSS : 2차원(행과 열)의 레이아웃 시스템 제공.

- Grid CSS Properties : gap | grid-template-columns | grid-template-rows | repeat | 1fr | grid-row-start | grid-row-end | grid-column-start | grid-column-end 

### display:table
- 요즘에는 float css, flex css, grid css를 사용하기 때문에 잘 사용하지는 않지만, 예전에는 display:table을 사용해서 레이아웃 많이 구현했음.
- 요소가 테이블처럼 작동. 따라서 table 요소와 tr, td와 같은 해당 요소를 사용하지 않고 HTML 테이블의 복제본을 만들 수 있음

### Position CSS
- Static : 기본값. 다른 태그와의 관계에 의해 자동으로 배치되며 위치 임의로 설정 가능
- Relative : 요소 자기 자신을 기준으로 배치 (원래 있던 위치를 기준으로 좌표 지정)
- Absolute : 부모 요소를 기준으로 배치 (절대 좌표로 위치 지정 가능)
    - 부모 요소에 `position: static`이 아닌 것이 있다면 : 그것을 기준
    - `position:static`이 아닌것이 없다면 : body를 기준
- Fixed : 스크롤과 상관없이 항상 문서 **최좌측 상단** 기준 (네비게이션 바를 생각하면 쉽게 이해)
- Sticky : 스크롤 영역 기준으로 배치
    - 스크롤 위치에 따라 static 요소와 fixed 요소 사이를 왔다갔다 함
    - 주어진 오프셋 위치가 뷰포트에서 만날 때까지 static하게 배치되다가 제자리에 fixed 됨
### z-index
- 앞과 뒤에 나타나는 요소를 결정
- Z-index가 더 높은 요소는 z-index가 더 낮은 요소 앞에 나타남 (음수도 가능)
- 기본 값 : 0
- 순서 값이 없을 경우, 코드상 순서에 따라 쌓임
- `position:static;` 스타일을 가진 요소는 항상 뒤에 나타남. Z-index 효과 x
- Z-index가 같거나 두 요소가 `position:static`이면 코드에서 나중에 작성된 요소가 앞에 나타남
- 부모에게 z-index 값을 줄 경우 부모끼리 먼저 z-index 순위를 정한 뒤 자식이 적용. 즉, 자식의 z-index 값이 아무리 높다 하더라도 부모의 값이 낮으면 위로 올라올 수 x
- Z-index는 position 속성을 지정하고 z-index 속성을 지정해야 함

### Media Query
- 화면 해상도, 기기 방향 등의 조건으로 HTML에 적용
- 반응형 웹 디자인 스타일로 기기마다(화면 크기마다) 전환 가능
- 기본 문법 : 선택적으로 미디어 유형과 and 또는 , 콤마 논리 연산자로 조건 적용 가능
``` @media [only 또는 not] [미디어 유형] [and 또는 ,] (조건문) {실행문} ```
- Min/max 사용 시 주의 사항
    - Min : 크기가 작은 순서대로 작성
    - Max : 크기가 큰 순서대로 작성

### CSS 적용 우선순위
1. !important를 붙인 속성
2. HTML에서 style을 직접 지정한 속성
3. #id로 지정한 속성
4. . 클래스, :가상 클래스로 지정한 속성
