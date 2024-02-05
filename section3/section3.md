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
