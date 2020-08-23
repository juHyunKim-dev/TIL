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

    >> justify-content: center;
    >> justify-content: flex-end;
    >> justify-content: space-evenly; 등등
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
