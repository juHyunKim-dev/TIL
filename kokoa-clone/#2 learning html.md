## [2] LEARNING HTML

```
파일명,폴더명은 항상 소문자로 작성한다!
 Tag(태그) -><열고> </닫고>
	·unordered list : <ul> </ul> (순서가 없는 목록)
		·list item(목록요소) : <li> </li>
	·ordered list : <ol> </ol>
		·list item(목록요소) : <li> </li>
	·anchor : <a> </a> 링크를 뜻함
	  tag에 추가하는 부가적인 정보 : attributes
	ex) href
	 <a href="http://google.com">
	ex) target="_self" , target="_blank"

	·<img /> : 이미지는 self-closing tag임.
	ex)src(소스)
	<img
	  src="https://~~~~~~"
	/>
	컴퓨터 안에 있는 이미지를 넣을때는 경로확실히하기
---------------------------------------------------
·규칙
	1.모든 html 파일은 <!DOCTYPE html>로 시작한다.
	2.<html>
	    <head>-웹사이트의 환경을 설정(외부적으로 보이지 않음)
	 	<title> ~~~`</title>
 		</head>
	       <body>-사용자가 볼 수 있는 content를 보여줌
	       </body>
	    </html>
	:: 브라우저 화면 상에 보여질 내용들은
		전부 body 태그에 있어야 한다::
---------------------------------------------------
·Its All About the Head
	::meta 태그 (self-closing)- meta:부가적인 정보
	meta 태그는 두개의 attribute를 가짐
	1. content
	2. name
   ex) <meta name="description" content="This is my website" />

   ::항상 <meta charset="utf-8" />넣기 - 글자가 깨지지 않게 함
   :: <html lang="kr"> <-사이트에서 사용되는 언어가 무엇인지 말해줌
----<head>는 사이트의 정보를 브라우저에게 알려주는 용도.
최대한 명확하게 우리의 웹사이트가 무엇인지 브라우저에게 알려줌
= 검색엔진이 이해할 수 있게 정리한다. ex)구글은 title과 description을 찾음

·	·<link rel="shortcut icon"
	          sizes="  "
	          href="   "
	/>  <-title옆에 사이트로고 넣어줌

	·<meta property="og.image" content="~~~.jpg" >
	카톡에 링크 공유했을때 보여지는 사진
--------------------------------------------------------------------
·More Tags
  :: 태그를 검색할땐 검색 키워드에 mdn 붙이기 - html tags mdn
	mdn사이트를 참고해서 사용
--------------------------------------------------------------------
·Form Tags
	<form> </form>
	<form>안에 form의 양식 만들어주기
	양식중에 제일 중요한 태그는 input
	<input />(self-closing)

	mdn에서 input에서 사용가능한 attribute확인하기

	input은 하나 혹은 여러 개의 type을 가질 수 있음.
	·placeholder
	·submit
	·type
	·value
	·disabled
	·required
	·minlength

      ex) <input placeholer="Name" type="text" />
              <input type="submit" value="Create Account" />
              <input required placeholder="Password" minlength="10"
	type="password" />
              <input type="file" accept=".png" />
 ::정리::
<tagname attrname="attrvalue"> adfdfadafd </tagname>
   태그이름    속성이름       속성값          content            태그닫기
if) 속성이 true or false (required)로 간단하다면 그대로 속성이름만 넣어도 OK
 <tagname required attrname="attrvalue"> dafdad </tagname>
----------------------------------------------------------------------
·More Tags and IDs
	·label -input과 함께여야 작동
	<label for="profile">Profile Photo</label>
	<input id="profile" required placeholer="Name" type="text" />
	*label의 for과 input의 id가 같은 값이어야 함.
	::태그 하나당 하나의 id만 가질 수 있음.
	::id의 값은 고유해야 함.
	id는 고유식별자이기 때문
----------------------------------------------------------------------
·Semantic HTML
	<div> </div> <-경계,division
	div는 박스라고 생각, 박스들은 양옆에 위치할 수 없음.
	·<span>-짧은 말을 위한 태그
	·<p> - 문단을 위한 태그
	::non-semantic 태그임(의미가 없는)

	·<header>-제목을 위한 태그
	·<main>- 본문을 위한 태그
	·<footer>-꼬릿말을 위한 태그
  ::모두 div로 처리해도 되지만 가독성을 위해 semantic태그로 작성
--------------------------------------------------------------------
· Recap
	어떤 attribute는 모든 태그가 사용가능
		일부 attribute는 특정 태그만 사용가능
```
