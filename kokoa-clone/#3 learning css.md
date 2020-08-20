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
    span {
    	display : block;
    	background-color: turquoise;
    }
    ```
    이렇게 설정하면 block으로 속성 변환.

> 어떤 요소가 inline이면 그 요소는 높이와 너비가 없음.

    block은 높이와 너비가 있음.
