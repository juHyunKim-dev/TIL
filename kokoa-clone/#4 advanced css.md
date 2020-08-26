### 4.0 Transitions <br>

어떤 상태에서 다른상태로의 변화를 _애니메이션화_ 하는 것<br>

**state가 없는 요소에 붙어야 함.**

        ex)
        transition: background-color 10s ease-in-out, color 5s ease-in-out;

-> background-color 와 color가 State(hover,active,focus 등등)에 있기 때문에 적용 가능.<br>

---

### 4.1 Transitions part Two <br>

- ease in function <br>

https://matthewlein.com/tools/ceaser <br>
사이트에서 효과 보기 가능 - cubic-bezier코드복사해서 그대로 적용

        ease-in
        ease-out
        ease-in-out

가장 일반적으로 사용하는 방법은 all <br>
but, 지정하고 싶다면 하고 싶은대로 가능, 단지 나눠서 써줘야 함. <br>
2개 이상을 지정하고 싶다면 transition의 끝에 콤마(,) 잊지말기 <br>

        ex)
        transition: color 1s cubic-bezier(0.6, 0, 0.735, 0.045),
        border-radius 5s ease-in-out;

---

### 4.2 Transformations <br>

_border-radius : 50%; -> Circle!_ <br>

**transform : 무언가를 '변형'시키는 것, 3D로 변형 가능** <br>

        transform : rotateY(85deg)
        -> Y축 85도 회전시키기 => 3D로 회전
        transform : rotateY(85deg) rotateX(20deg) rotateZ(10deg);

        transform : scale( 2, 2 );
        -> 크기 변경(x,y방향으로 2배씩)

        transform : translateX(-60px);
        -> 왼쪽으로 60px 옮기기

**_주의_** <br>
translate에서 이 명령어는 transformation을 적용시키긴 하지만 다른 형제(sibling)를 변화시키지 않는다.<br>
-> 이미지와 글씨가 일직선 상에 있을때, 이미지를 transform : translate 하면 텍스트는 이동하지 않고, 이미지는 텍스트위로 겹침.<br>

페이지의 픽셀을 변형시키는 것이기 때문에 Transformation은 다른 box element, 이미지에 영향을 끼치지 않음.<br>
margin, padding도 적용되지 않음. 일종의 _3D_ transformation이기 때문 <br>

다른 요소의 box를 변형시키지 않고 원하는 요소를 이동시키기 위해서 사용하는것 <br>

**transition과 연계해서 사용하기!**

-> transition으로 transform을 적용하자.

        transition: transform 5s ease-in-out;

**transition은 root에 있어야 한다!!**

참고 사이트 _transform mdn_ <br>
여기서 복사해서 사용 가능.<br>

---

### 4.3 Animations part One <br>

transition : 어떤 상태(state)에서 다른 상태(state)로 변하는 것을 애니메이션으로 만듦. <br>
하지만 마우스를 올렸을 때만 볼 수 있음. <br>

But, 계속 재생되는 애니메이션을 얻고 싶으면 어떻게 해야 할까?<br>
(마우스를 위에 올리거나, transition없이)<br>
=> 애니메이션 사용!<br>

**애니메이션에는 2가지 옵션이 있다**

1.  from{} to {}

        [ex.1]
        @keyframes 애니메이션이름 {
        from {
        transform: rotateX(0);
        }
        to {
        transform: rotateX(360deg);
        }
        }
        img {
        border: 10px solid black;
        border-radius: 50%;
        animation: 애니메이션이름 5s ease-in-out;
        }

        [ex.2]
        @keyframes 애니메이션이름 {
        from {
        transform: rotateY(0);
        }
        to {
        transform: rotateY(360deg);
        }
        }
        img {
        border: 10px solid black;
        border-radius: 50%;
        animation: 애니메이션이름 5s ease-in-out _infinite_;
        }
        -> infinite 쓰면 무한으로 반복재생. <br>

**_from {} to {} 옵션은 시작할 때 원위치에서 시작_**

2.  %주기

        ex)
        @keyframes 애니메이션이름 {

        0% {
        transform: rotateY(0);
        }
        50% {
        transform: rotateY(180deg) translateX(100px);
        }
        100% {
        transform: rotateY(0);
        }

-> 이런식으로 표현하면 되돌리기를 표현할 수 있음<br>
원하는 만큼 많은 스탭을 가질 수 있음 (0,25,50,75,100% 등등)<br>

_animista.net_ 사이트 참고하기<br>

(참고) 자주쓰는 옵션에는 [ opacity : 0; ] 가 있음<br>

---

### 4.5 Media Queries <br>

=> Responsive Design(반응형 디자인)<br>
**media query는 코드의 조건을 추가할 수 있는 방법, 조건이 참이라면 이 CSS를 실행하라** <br>

오직 CSS만을 이용해서 웹사이트를 보고 있는 사용자의 스크린 사이즈를 알 수 있음

- landscape모드( 가로모드)
- portrait모드 (세로모드)

        @media screen and (min-width:650px) and (max-width : 800px){
        div {
        background-color :tomato;
        }
        }

        @media screen and (orientation : landscape) {
        span {
        display : none;
        }
        }
        -> 화면이 가로모드일 때 span 보여주지 않음.

---

### 4.6 Media Queries Recap <br>

1.  media query의 사용 형식 기억하기

        @media media-type(보통은 screen) and (코드조건) {
        element {
                    CSS
                }
        }

!! media query 안 element에 css를 적용시켜야 한다.<br>

2.  media query는 and를 써서 연결됨.

        @ media screen and (min-width: 650px) and (max-width:800px)

3.  media query 중 핸드폰에만 적용되는 것들이 있음. <br>
4.  CSS media query MDN 구글링하면 많은 예시가 존재. <br>
5.  media-type 에는 screen, print등이 있다. 보통 screen을 사용 <br>
