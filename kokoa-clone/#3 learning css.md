## [3] LEARNING CSS

```
html과 css를 섞는 법 2가지
 1. 같은 html 파일에 css 두기
	head 안에 style 태그 추가하고 그 안에 CSS코드 작성
	<style> ~~~css~~~~</style>

 2. css와 html을 분리하기
	**추천**분리된 파일을 가지게 되면 이 파일을
	다른 많은 HTML 페이지에서 사용할 수 있기 때문

 	css파일 만들기(styles.css)
	link 태그를 이용해서 파일을 연결
	<link href="styles.css" rel="stylesheet" />
---------------------------------------------
·Writing Our First CSS Lines
		·selector-가리키는 대상(태그 지정)
		·property<- 띄어쓰기, _, / 금지
	 	[ propername : propervalue;  ]
	ex) h1 {
		color: blue;
		font-size: 20px;
		text-decoration : underline;
		text-align: center;
		}
---------------------------------------------
·What Does Cascading Mean
	·CSS(cascading style sheet) : 브라우저가
	 CSS코드를 읽을 때 위에 있는 코드부터 차례로 읽음
 	따라서 맨 마지막에 있는 코드가 최종적으로 적용됨.
---------------------------------------------
·Blocks and Inlines
	두 종류의 형태가 존재
	block은 옆에 아무 것도 올 수 없음(대부분)
	inline은 같은 줄에 위치할 수 있음(span,link,image)
```

---

### Margin Part One

> _block을 inline으로 바꾸기 가능할까?_

= display 속성을 사용하자

ex)기본적으로 span의 display속성은 inline인데,

```html
span { display : block; background-color: turquoise; }
```

이렇게 설정하면 block으로 속성 변환.

> 어떤 요소가 inline이면 그 요소는 높이와 너비가 없음. -> ~~box~~

    block은 높이와 너비가 있음. -> box

##### **box의 특징 3가지**

**1. margin**

> box의 border(경계)의 **바깥**에 있는 공간

- 값이 하나면 전체
  margin : 20px;
- 값이 두개면 '상하, 좌우'
  margin : 20px, 10px;
- 값이 네개면 위,오,아래,왼(시계방향 순서)
  margin : 20px, 10px, 20px, 10px;

---

**_collapsing margin_**

![참고사진](https://ifh.cc/g/4dos4u.png)

흰 box의 경계가 보라색 box의 경계와 같을 때 일어나고, 그때 두 box의 margin은 하나가 된다.
(위,아래쪽만 일어남)

---

**2. padding**
padding은 margin과 반대 개념

> box의 border(경계)로부터 **안쪽**에 있는 공간

- _요소간에 차이를 주는 방법 = id_ <br>
  id를 가리키는 방법 -> #뒤에 id명 쓰기 <br>
  CSS 코드의 id명은 HTML 코드의 id명과 같아야 함.

- 이번강의 코드

```html
<!DOCTYPE html>
<meta charset="utf-8" />
<html lang="kr">
  <head>
    <title>practice</title>
    <style>
      html {
        background-color: darkolivegreen;
      }
      body {
        margin: 20;
        padding: 20px;
        background-color: orangered;
      }
      div {
        padding: 20px;
        height: 150px;
        width: 150px;
        background-color: wheat;
      }
      #first {
        height: 150px;
        width: 150px;
        background-color: orchid;
      }
      #second {
        height: 100px;
        width: 100px;
        background-color: powderblue;
      }
      #third {
        height: 50px;
        width: 50px;
        background-color: royalblue;
      }
      #fourth {
        height: 25px;
        width: 25px;
        background-color: burlywood;
      }
    </style>
  </head>
  <body>
    <div id="first">
      <div id="second">
        <div id="third">
          <div id="fourth"></div>
        </div>
      </div>
    </div>
  </body>
  <html></html>
</html>
```

**3. border**

> border은 말그대로 box의 경계 <br>

border style MDN으로 검색하면 여러 style옵션을 볼 수 있음.

```html
* { border: 2px dashed black; }
```

"\*"표시는 전체를 뜻함.<br>
border는 inline과 block 모두에 적용됨.<br>
CSS의 cascading한 성질을 이용할 수 도 있음.<br>
이때 너비부터 차례대로 다시 쓸 필요 없이 border-style 로 지정가능

```html
span { border-style:dotted; }
```

span은 inline이기 때문에 높이와 너비가 없음.<br>
그래서 위, 아래에 margin을 가질 수 없다.<br>
padding은 사방에 다 가질 수 있음.<br>
margin은 좌우로만 가질 수 있음.

---

### 3.8 Classes <br>

[#id명] 대신에 사용할 수 있다.<br>
id는 고유의 값을 가져야 하는데 class는 요소를 가리킬 수 있으면서 겹쳐도 된다!<br>
**[.class명]** <br>
(.)은 class명이라는 뜻, 따라서 <br>

```
#tomato는 id="tomato"
.tomato는 class="tomato"
```

**_특징_**

> - class명은 유일할 필요가 없다
> - 여러 요소들이 같이 쓸 수 있다.(공유 가능)
> - 한 번에 여러 class가 쓰일 수 있다.

---

border-radius: 5px; -> 모서리 둥글게 <br>

```html
<!DOCTYPE html>
<meta charset="utf-8" />
<html lang="kr">
  <head>
    <title>practice</title>
    <style>
      body {
        padding: 20px;
      }
      .btn {
        border-radius: 5px;
        padding: 20px;
      }
      .free {
        background-color: blue;
        color: whitesmoke;
      }
      .happy {
        background-color: pink;
      }
    </style>
  </head>
  <body>
    <span class="free btn">get off work</span>
    <span class="happy btn">get off work</span>
    <span class="free btn">get off work</span>
    <span class="happy btn">get off work</span>
    <span class="free btn">get off work</span>
    <span class="happy btn">get off work</span>
  </body>
</html>
```

---

### 3.9 Inline Block <br>

div는 기본적으로 block <br>
이 display를 inline으로 바꾸면 아무것도 안보임 -> inline은 너비랑 높이를 가질 수 없기때문 <br>
inline-block은 inline을 block으로 인식하게 함. 높이o, margin o, 바로 옆에 다른요소 o <br>
inline-block의 디폴트 값은 이상하고 불편함, 정해진 형식이 없음. <br>
_inline-block은 Responsive Design을 지원하지 않는다.-> 창 크기에 영향을 받음._ <br>

```
div {
	display: inline-block;
	width: 50px;
	height: 50px;
	background-color: teal;
       }
```

---

### 3.10 Flexbox Part One <br>

**flexbox**는 박스들을 어떤 곳이든 둘 수 있음, 아주 유연함. 2d 레이아웃에서 잘 작동<br>
**[지켜야 할 3가지 규칙]** <br>

**1. 자식 element에는 어떤 것도 적지 말아야 함. 부모 엘리먼트에만 명시하기**<br>
ex) div의 부모는 body<br>
부모 엘리먼트를 flex container로 만들어야함.-> body {display: flex;} <br>
엘리먼트들은 여전히 block이지만 body가 자식들을 제어할 수 있음. <br>

> justify-content 속성
>
> > justify-content: center;<br>
> > justify-content: flex-end;<br>
> > justify-content: space-evenly; 등등

박스의 공간을 자동으로 계산해줌. 그래서 화면 크기를 작게 만들어주면 빈 공간 크기도 작아짐<br>

**2. 주축과 교차축** <br>
flexbox에서 기본적으로 축들이 가지는 모습 <br>
justify-content는 주축에 적용됨.<br>
align-items는 교차축에 적용됨.<br>
기본적으로 교차축은 수직 -> 나중에 속성을 바꿀수도 있음<br>
<br>
body의 크기도 생각하기<br>
body { height :100vh; }<br>
vh는 viewport height를 말하는데 viewport=screen<br>
100vh는 화면 높이의 100%를 말함.<br>
align-items : flex-end;<br>
align-items : flex-start; <-기본값 <br>
<br>
**[정리]**<br>
justify-content와 align-items를 적용하고 싶으면 display:flex를 해줘야 함.<br>
그러면 해당 엘리먼트인 body가 flex컨테이너가 될거임.<br>
flex 컨테이너는 두 개의 축을 가지는데 주축과 교차축<br>
디폴트로 주축은 수평, 교차축은 수직임.<br>
justify-content는 주축 align-items은 교차축이 적용됨<br>

---

### 3.11 Flexbox Part Two <br>

1. 주축(main axis)와 교차축(cross axis)는 디폴트로 수평, 수직임.
   이걸 바꾸기 위해서 *flex-diretion*을 수정하자.
   두가지 옵션 row와 column이 있는데, 디폴트로 row<br>
   column으로 하면 주축이 수직, 교차축이 수평

2. 부모 엘리먼트를 flex 컨테이너로 했을 때 -> 자식 엘리먼트들도 flex 컨테이너가 될 수 있음<br>
   자식 엘리먼트를 flex 컨테이너로 한 경우 자식 엘리먼트의 내용에 영향

3. flexbox의 속성 더 알아보기<br>
   wrapping : flex-wrap으로 설정을 바꿀 수 있음 <br>
   flex-wrap: nowrap (디폴트값) 모든 요소를 같은 줄에 있게 만들어준다.<br>
   flex-wrap: wrap 명시된 사이즈로 반영해서 화면 사이즈에 따라 다음줄로 옮김.<br>
   <br>
   flex-direction : column-reverse ->밑에서 시작해서 위로 올라감 (ex. 3, 2, 1) <br>
   flex-direction : row-reverse
   flex-wrap: wrap-reverse

**flexbox는 박스를 배열하는데 유용함**

### 3.12 Fixed <br>

position 이라는 속성이 존재<br>
position : fixed -> 화면을 스크롤해도 박스가 같은 위치에서 따라다님<br>
기본적으로 같은 레이어에 위치하다가 top,left,right,bottom이라는 프로퍼티 중에서 하나만 수정해도 다른 레이어로 넘어감.<br>
레이어 위의 레이어에 존재(제일 위 레이어)<br>

---

### 3.13 Relative Absolute <br>

position : static 레이아웃이 박스를 처음 위치하는 곳에 두는 것 <br>
**position: _relative_ -> element가 처음 위치한 곳을 기준으로 수정하는 것**
top,bottom,left,right 속성 사용 가능<br>

    position: relative;
    top : -10px;

**position : _absolute_ -> 가장 가까운 relative부모를 기준으로 이동함.** <br>
그래서 relative한 부모를 찾지 못하면 body를 기준으로 이동.

---

### 3.14 Pseudo Selectors part One <br>

Pseudo Selector : 좀 더 세부적으로 엘리먼트를 선택함. <br>
보통 엘리먼트를 선택할때는 #id나 .class사용 <br>
하지만 _pseudo selector는 html은 건드리지도 않고, css만으로 가능함._<br>

    ex)
    div:firtst-child {}
    div:last-child {}
    span:nth-child(2), span:nth-child(4){}
    => span:nth-child(even) {} 짝수 다 적용
    span:nth-child(odd) {} 홀수 다 적용
    2n+1, 3n, 등과 같은 수식 적용가능

---

### 3.15 Combinators <br>

전체 html코드의 흐름이 다음과 같을 때,

```html
<div>
  <span></span>
  <p>
    <span></span>
  </p>
  <span></span>
</div>
```

    ex) p span { }
    -> p안에 있는 span을 말함. 이때 p는 부모 selector, span은 child selector
    ex) div > span { }
    -> 부모와 direct children의 관계
    ex) p + span { }
    -> 형제와 바로 뒤에 오는 형제의 관계
    ex) p ~ span
    -> 형제와 형제관계 꼭 바로 뒤에 올 필요는 없음.

---

### 3.16 Pseudo Selectors part Two <br>

**:: attribute** <br>

```
input:required { border : 1px solid tomato;}
input:optional { border : 1px solid wheat;}
=>
input {
border: 1px solid wheat;
}
input : required {
border-color : tomato;
}
```

- attribute seletor : attribute를 통해 어떤 것이든 선택할 수 있게 해줌
  ex)
  input [type="password"] {
  background-color : teal;
  }

  input [placeholder="username"] {
  background-color : pink;
  }

  input [placeholder~="name"] {
  background-color : yellowgreen;
  }
  -> "name"을 포함한 모든 input을 지정한 것.

---

### 3.17 States <br>

    button:active {
    background-color : tomato; - 커서로 클릭하면 적용
    }
    button:hover { } - 커서 위에 올리면 적용
    button:focus { } - 키보드로 선택되었을 때 적용

<br>
    visited - 링크에만 적용됨.
    a:visited {
        color: tomato;
        }
    -내가 방문했던 링크에 적용됨. ( ·anchor : <a> </a> 링크를 뜻함, tag에 추가하는 부가적인 정보)
<br>
    focus-within
    -> focused인 자식을 가진 부모 엘리먼트에 적용
    자식이 focused 될때 부모엘리먼트가 변함.
    ex) form : focus-wtihin
<br>
```html
form : hover input { 
  background-color : pink; 
  }
```
- form이 hover상태가 되면 input이 바뀜<br>
  부모의 state에 따라 자식을 바꾸는 것.<br>
다음과 같이도 적용 가능
```html
 form : hover input : focus { 
  background-color : pink; 
    }
```
------

### 3.18 Recap <br>

<pseduo element 3개>

1. ::placeholder <br>
   ex) input :: placeholder { color : blue; }

2. ::selection (드래그하면 변환) <br>
   ex)p :: selection { color: white; background-color : red; }

3. ::first-letter, ::first-line 등등 <br>

**Recap** <br>

> state
>
> > :hover
> > :active
> > :focus
> > :visited
> > :focus-within

> combinator
>
> > 부모 자식 ( )
> > 부모와 바로 밑 자식 (>)
> > 형제와 바로 다음 형제 (+)
> > 형제와 형제(~)

> attribute 사용
>
> > input[] : []안에 아무거나 적용 가능

> > ex) input[type="password"] { background-color:green; } <br>
> > -> password라는 type을 가진 input만 선택

---

### 3.19 Colors and Variables <br>

- color

1. hex code <br>
   : #fcce00 등등
2. rgb <br>
   : rgb(252, 206, 0);
3. rgba <br>
   : rgb에 a(alpha-투명도(0~1))를 더한 것

크롬 extension으로 color picker 사용하면 좋음.

- variable( = custom property)

_:root라 불리는 element에 변수 추가하기_<br>
:root는 기본적으로 모든 document의 뿌리임<br>
**변수이름짓기 : [--변수-이름]**<br>
빈 공간이 있으면 -로 채워야 함.<br>
**사용하기 : var(--변수-이름)**<br>

ex)대략적인 코드 (완벽X)

```html
<head>
  <style>
    :root {
      --main-color: #fcce00;
      --defalut-border: 1px solid var(--main-color);
    }
    a {
      color: var(--main-color);
    }
  </style>
</head>
<body>
  <div>
    <a href="#">website</a>
  </div>
</body>
```
