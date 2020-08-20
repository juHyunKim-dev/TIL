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
  id를 가리키는 방법 -> #뒤에 id명 쓰기
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
