# basicFrontend

## 복습용 README.md 


## 1. HTML 
``` js
// <table> 만들어 놓으면 중간에 tbody 껴있음
// 이거 고려하고 탐색
// <table> tbody <tr> <td>

엔터도 공백이다. ( 그래서 엘리먼트를 여러라인으로 두면 공백이 조금 생기는데 font-size를 0으로 두면 해결됨 )

공백은 &nbsp; 
&기호는 &amp; 이다.  ( 이거는 스프링 xml에서 url처리시 쓰임 )
// 오른쪽 기준이라는거 생각하면 안헷갈림
&lt; less than        < 
&gt; greater than     >
&copy; 
&#65;  : 문자코드 


// mybatis 다룰 때 아래 지식이 필요 
PCDATA > xml로 해석 한다. > 변환작업 일어남
CDATA  > xml로 해석 안한다. 
// <![CDATA[  ]]> 

body 태그 자체는 bgColor, background(이미지)속성가진다.

p 태그 > <p align ="justify">첫번째 문단입니다.</p> // justify 쓸만하다. 

html 스타일 태그: 이건 암기 

<ul> / <ol> : type 속성으로 스타일을 줄 수 있다. 

왼쪽 여백의 원인은 'padding'
list-style-type: none으로 bullet 제거 

<a href="ex10_list.html" target="_blank">열번째 예제(self)</a>
// _blank는 새창에서 열기

<a href="ex10_list.html" target="_self">열번째 예제(self)</a>
// _self는 현재창에서 열기 

<li><a href="#item1">변수</a></li>
# 을 붙이면 앵커라는 건데 한 페이지 안에서 
어떤 태그로 이동할 수 있다. 

* 어떤 태그가 a태그면 a태그의 name 속성명으로 '#속성명' 지정
* 어떤 태그가 div 같은거면 id속성의 속성명으로 지정

// alt는 깨진 이미지 나올 때 이게 뭔지 대체구문
<img src="images/dog01.jpg" alt="강아지 오형제">
// width, height 속성을 제공 

태그는 style 인라인 속성 지정을 하는 경우가 있음
<a href="#"style="background-color: yellow;">인라인태그 링크2</a>

<table> 구성 : table, thead, tbody, tr, th, td, tfoot 
<table> : border를 1로 지정시 경계가 보임, bgColor 속성도 있다. 

<td> : 속성으로 align="center"로 좌우 정렬가능, valign="center"으로 상하 정렬가능
   
테이블 병합 (헷갈리지 않아야 함)
* td에서 쓴다 : 
rowspan > row를 합치겠다.
colspan > col을 합치겠다.

★ rowspan이나 colspan을 쓰고 다음 tr 쪽에 td를 보면서 개수를 맞춰야 함 


<form></form> 태그 : method속성(get, post), action(url)속성 제공, onsubmit속성( ☞ 내가 작성한 자바스크립트 함수 호출 )

ex)
<form action="/action_url.php" onsubmit="fn();">
블라블라
</form>

스크립트 단에서 코드 짤 때 form 태그에 submit 이벤트가 감지되면 양식을 제출하는 고유동작(페이지 이동 or 새로고침 발생)이 일어나는데 이것을 event.preventDefault();로 막아준다. 

<input> 태그 

input.type : 입력 컨트롤의 종류
text, password, checkbox, radio, file, hidden, [ submit, reset, button : 버튼계열], date(ex20.html 참고), color(색상선택창), 
tel, url, email


input.size
input.maxlength
input.readonly
input.disabled
input.value
input.accesskey : 이걸 "s" 라 주고 alt+s 누르면 바로감
input.autofocus : 새로 고침시 바로 포커싱
input.autocomplete : 이전에 입력한 검색어 보여줌 그래서 자동완성이 가능

input.placeholder : 입력전에 이미 들고있는 값 
input.required : 내용물 채워야 submit 가능
input.onchange : 내용물 변경 감지
input.min, input.max : 범위


숫자: <input type="number" min="0" max="100" step="10">
// 위아래 화살표가 생김, step을 줘서 몇씩 증가 감서 인터페이스 제공
input.step : 몇씩 

// 진행바
<progress></progress> 

// 수치표시
<meter value="0.5"></meter> 

// 클릭시 세부내용 보여줌 
<details>
    <summary>자바?</summary>
        <p>자바는 어쩌구 저쩌구 어쩌구 저쩌구</p>  
</details>

<select>
    <option></option>
</select>

// label 태그는 input의 id를 for로 받는다. 
// 그러면 한 덩이로 묶인다. 
<input type="checkbox" id="cb1"> <label for="cb1">영화</label>

```

## 2. CSS


### selector 
``` js
#id    : id는 고유한 속성을 가짐 
.class : 재사용 가능성 있음
tag   

선택자 두개 붙여쓴거 : 한 태그에 같이 적용된것 
.class1.class2 


#span1,
#div1 { // ,로 여러개 지정도 가능
    background-color: yellow;
}

자식 선택자 vs 자손 선택자
자식 선택자 (>)
자손 선택자 ( 스페이스 )

인접 형제 선택자 (+) : 형제중에서 인접한 녀석들만 OK
형제 선택자 (~) : 인접하지 않더라도 형제중에서 그 녀석이 있으면 OK
ex) div + span 
ex) div ~ span 

의사 클래스, 실제 태그에 class 속성에 명시되진 않았음

a:link : 브라우저가 한번도 방문하지 않은 상태
a:visited : 브라우저가 방문했던 상태
a:active : 활성화가 된 상태
a:hover   : 마우스 커서가 올라가 있는 상태

input 태그에 
input:focus{} // 이렇게 걸어도 됨

선택자 충돌 
css 라이브러리 쓰다보면 많이 일어남
선택자 점수를 항상 염두해야 한다.
선택자 충돌이 일어나는 경우 선택자 점수에 따라 우선순위 결정
태그 : 1점, 클래스 10점, 아이디 100점 정도? 
근데 태그가 100개 있어도 클래스 하나는 못이김 

Emmet 

// 자동 완성 툴 
div#box1.box
<div id="box1" class="box"></div>

div[title=상자] // 속성 선택자는 이렇게 근데 ""안넣는다. 
<div title="상자"></div>

img[src=cat.jpg alt=고양이 width=200 height=150]
<img src="cat.jpg" alt="고양이" width="200" height="150">

div#box$${상자}*3
<div id="box01">상자</div>
<div id="box02">상자</div>
<div id="box03">상자</div>
	 
// 곱하기는 바로 앞에 요소에만 적용되서 괄호를 붙여야 한다. 
(h1+p)*3 
<h1></h1>
<p></p>
<h1></h1>
<p></p>
<h1></h1>
<p></p>


// + 형제선택자(+)는 지원하나 인접선택자(~)는 지원 안한다.
h1#title1.title{제목입니다.}+p.content{설명입니다.}*2
<h1 id="title1" class="title">제목입니다.</h1>
<p class="content">설명입니다.</p>
<p class="content">설명입니다.</p>
// *2가 바로 옆에태그만 붙어서 일렬로 된다. 

<!-- 자식 선택자 -->
a > b : 자식 > 지원(O)
a b   : 자손 > 지원(X)
// 자식 선택자는 지원되나 자손 선택자는 어디까진지 모르니까 지원 안되는 것 

table#tbl1>tr*2>td.cell${항목$}*2
<table id="tbl1">
    <tr>
        <td class="cell1">항목1</td>
        <td class="cell2">항목2</td>
    </tr>
    <tr>
        <td class="cell1">항목1</td>
        <td class="cell2">항목2</td>
    </tr>
</table>


(h1>lorem1)+(p>lorem2)*3
<h1>Lorem.</h1>
<p>Lorem, ipsum.</p>
<p>Deleniti, sapiente!</p>
<p>Soluta, fuga.</p>
// 제목, 문단1, 문단2, 문단3 정의

//배경
background-color : red, rgb(255, 0, 128), rgba(255, 255, 255, 1)
background-image : url('images/cat01.jpg'), url(images/cat01.jpg)
                   // '' 써도 되고 안써도 되고 
// 이미지가 짝으면 defautl로 여백 채우려고 반복하는데 이거 no로 하면 반복 안함                   
background-repeat: no-repeat; 


background-position: center center; // 배경의 위치점을 정함 
background-position: right top;
background-position: 200px 200px;

background-attachment: fixed; // 스크롤이 움직여도 배경 이미지 고정

// 글꼴 가져다 쓰기 
@font-face {
font-family: 'BMHANNAPro';
src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_seven@1.0/BMHANNAPro.woff') format('woff');
font-weight: normal;
font-style: normal;
}

폰트쓰겠다고 cdn으로 선언하고
아래처럼 쓰면 됨 > 위에 이름 복붙 
font-family: 'BMHANNAPro';

font-variant: small-caps;  // all 대문자인데 앞 글자는 큰 대문자

Box 
border-style,
width,
color

박스의 크기는 다음과 같이 결정 된다. 
★★★ content + padding + border + margin

border-collapse: separate; // 분리됨  
border-collapse: collapse; // 한줄임


overflow: visible; /* 넘친걸 보여줘 */

overflow: hidden;  /* 넘친걸 숨겨줘 */ > transform, animation과 응용가능

overflow: scroll;  /* 스크롤바가 생긴다. 무조건 스크롤바를 확보한다.  */

overflow: auto;   /* 안보이다가 내용 많아지면 생김 */

// 안보이게 해주는 스타일
visibility: hidden;  
display: none;  


★★★ display
block: width, height, margin 줄 수 있다. 너비는 default 로 100%

inline : width, height, margin 줄 수 없다. 너비는 내용물만큼

inline-block : block + inline 속성 다가짐

★ inline에 float를 주면 inline에도 마진을 줄 수 있다. 

배치 : 기본적으로 float로 배치함

혹은 flex나 grid로 배치함 

▶ float를 줘버리면 중간에 비는 공간을 다른요소가 그 자리로 치고 올라올 수 있다. 그래서 clear 속성을 주는 경우가 있음 
clear:left, right, both; 를 주면 float의 성질을 제거한다. 

♣ clear를 쓸 때 float과 동시에 쓰지 않도록 주의하자 
// clear를 썼는데 알고보니 위쪽 style에 float 걸린 상황 조심

예시 ) 
<div class="newsContent"></div> // 얘는 float된 애
<div style="clear:left;"></div> // 얘는 float안된 애

//★ clear를 아래처럼 줘도 된다. 
.navernews::after{
    content:'';
    display: block;
    clear :left;
}

★ float의 문제 부모요소는 자식요소들이 float를 해버리면 알아차리지 못한다. 무의식적으로 자식들이 부모 영역에서 빠져나가 버린다. > overflow

> purecss라는 라이브러리가 있음 


※ 가운데 정렬

무엇을 가운데로 정렬 할거냐?

[ 텍스트 ] 
1. block : 한 block은 100%의 width를 가지므로 block안의 text는 text-align : center; 가 먹힌다.

2. inline : 인라인 태그 안에서는 내용물 만큼의 공간만을 차지함
그래서 인라인 태그 안에 text는 가운데 정렬이 불가능

[ 블럭 ]
1. block : 부토 div가 있고 자식 div 있을 때 자식 div 정렬
자식 div 태그에 width를 일정 크기만큼 주면 부모 div 태그안에서 자식 div 태그가 움직일 공간이 나오면 그 때 margin:auto 걸어버리면 가운데 정렬된다. 
[ inline ] : text-align 을 쓰자 


※ 가상클래스 ( 중요 ! )
1. :first-child > 자신이 자신의 그룹에서 첫번째 자식인지?
' 형제들중에서~~~~ ' 나눈 몇번짼가? 라는 말이 숨어있다. 
2. :last-child
3. :nth-child(n)
4. :nth-last-child(n)

li:nth-child(n) // 전부다 건다. 
li:nth-child(2n+1) // 홀수만 건다. 
li:nth-child(odd)
li:nth-child(2n) // 짝수만
li:nth-child(even)
li:first-child
li:nth-child(3)

.tbl tr:nth-child(even) td:nth-child(odd) // 이런식으로 도 선택자를 잡을 수 있다. 중간에 가상 또 가상 


속성 선택자
1. 선택자[속성명]     : 해당 속성을 명시했는지?
2. 선택자[속성명=값]  : 해당속성과 값을 명시했는지? 속성의 값이 맞는 걸로도 찾음 
3. 선택자[속성명^=값] : 속성명이 이 값으로 시작하는 애로 찾아주세요. startsWith()
4. 선택자[속성명$=값] : 속성값이 값으로 끝나는지? endsWith()
5. 선택자[속성명*=값] : 이 값이 들어있는 친구를 찾아주세요. 속성값이 포함되는데 contains() or like '%값%'

.list a[target] {background-color: gold;}
.list a[target=_black] {background-color: gold;} 
.list a[href^=https] {background-color: gold;} 
.list a[href$='.com'] {background-color: gold;}
.list a[href*=m] {background-color: gold;}
 /* . 이 있으니까 escape를 시켜주기 위해서 ' '안에다가 씀 . */


★ 셀렉터를 아래처럼도 약간 동적인 느낌으로도 걸 수 있다. 
input[type=checkbox]:checked
.cb-cat:checked + .cat
.cb-cat + .cat
.cb1:checked + div


★ 전후 선택자
1. ::before = :before
2. ::after  = :after
span::before{
    content: '[';
}
span::after{
    content: ']';
}

★ 그림자 효과 
text-shadow: 2px 2px 10px #999;
box-shadow: 5px 2px 2px gray;

border-radius : px or %, 50%정도면 원처럼 됨

★ column 내용물을 컬럼기준으로 분할한다. 
p {
    column-count: 3;               /* 3단의 컬럼으로 나눠진다.*/
    column-gap: 20px;              /* 간격이다. */
    column-rule: 1px solid gray; /* 테두리다. */
    text-align: justify;           /* 양끝 맞춰진다. */
}


border : 경계인데 
box-sizing: border-box; 쓰면 width, height 기본 크기 보장 (예상 사이즈임)
box-sizing: content-box; 쓰면 width, height가 컨텐츠 크기 보장 (좀더 커짐)

outline : 무조건 바깥쪽 테두리.


// CSS 변수 지정 
:root {  
    --main-background-color : #dad7cd;
}

// 쓸 때는 var() 안에다가 
body {
    background-color: var(--main-background-color);
}

// 미디어 쿼리
@media (max-width: 767px){} // max니까 여기까지는 이걸로 해줘
// 767px크기 까지는 이 정의로 해줘라 


@media (min-width: 768px){} //min이니까 
// 최소 768크기부터는 이 정의로 해줘

가로모드 스마트폰 너비(576px ~ 767px)
    @media (min-width : 576px) {
}
태블릿 너비(767px ~ 991px)
    @media (min-width : 768px) {
}

데스크탑(랩탑)
@media (min-width : 992px) {
    color : red;
}
큰화면 데스크톱
@media (min-width : 1200px) {
    color : skyblue;
}

input 태그나 textarea 태그에 
outline :none; 걸 수 있다.
resize :none;도 걸 수 있다. 

```

## 3. Javascript

### BOM
``` js
//<img src="../css/images/catty01.png" name="cat1">
// <a href="http://naver.com" name="link1">네이버</a>
//<form name="form1"> <input type="text" name="txt1">   </div> </form>

window.document.images
window.document.form1.txt1

window.document.all.btn1 // all은 다 들고 있다. > name 참조가능 
window.document.images   // 이미지를 들고 있다. images[0] 방식 혹은 images['cat1'] 방식으로 참조

// 앞에 window는 생략가능하다. 

document.links['link1'].href= 'http://google.com'; // 링크에 대한 정보는 links에 

window.open() // 창 id, 창 속성부여가능(크기,위치)
window.close()
★ 자식창에서 부모창으로 접근시 opener. 으로 접근 

// 창의 크기 높이, 너비 정보 제공
window.screen.availWidth
window.screen.availHeight

window.location.host
window.location.hostname
window.location.protocol
window.location.port

window.location.href ="주소 or html자원"

window.location.reload(); // 새로고침
window.location.assign('주소')  // 얘도 해당 주소로감
window.location.replace('주소') // 이 친구는 history를 안남김

// 링크 이동 history를 참조해서 이동한다. 
// ★ 게시판 만들 때 사용가능
window.history.back(); // 
history.forward();
history.go(-2);
history.go(2); 
```

★ BOM으로 얻은 객체와 DOM으로 얻은 객체는 서로 동일하다. ( 그러나 Jquery 객체는 다른 객체다. )

### DOM 검색 메서드 
``` js
getElementById > id를 검색
getElementsByClassName > class 검색
getElementsByName > 이름 검색
getElementsTagName > tag 이름 검색
querySelector > 선택자 검색인데 좋은 점이 부모 자식 이런거 고려해서 검색 가능
querySelectorAll 
// s 붙은거, querySelectorAll은 여러개 반환, querySelector는 맨처음 발견한거 한개 반환

```
### DOM에서 노드탐색
```js

// <div id="me"></div> 이게 있다고 가정

// 1. className 클래스 이름 가져옴 
const me = document.getElementById('me');
me.className = 'check'; // 이래버리면 
// <div id="me" class="check"> 이거임
//2. me.childNodes : 자식 노드들 가져옴 > 배열(length로 길이 체크) > 태그 아닌 친구도 포함
//3. me.children : 자식 태그들임 > 배열 > 태그만
//4. nodeType으로 어떤 종류인지 물어본다. 
// me.childNodes[i].nodeType > 숫자값 나옴
//5. nodeName으로 무슨 태그인지 태그 이름 알 수 있다. ex) me.childNodes[i].nodeName, 'DIV', 'TD' 대문자다!!

// child에서 아래의 종류의 노드는 정의되어 있음
// firstElementChild 
// lastElementChild

// 부모 & 조상
// me.parentNode : 태그가 아닌 친구도 포함
// me.parentElement // 태그만 
// parentNode나 parentElement, childNodes잘 섞어쓰고 체이닝 하면 형제 찾을 수 있음

// 바로 위 형제 
// me.previousSibling
// me.previousElementSibling

 // 바로 밑의 형제 
// me.nextSibling
// me.nextElementSibling


// document.elementsFromPoint(x, y)
// document.elementFromPoint(x, y)
// 특정 좌표에 어떤 태그 있는지 알려주는 함수 

// alert(document.elementsFromPoint(x, y)[0].nodeName); > 무슨 태그가 있는지 확인


// 콘텐츠 조작 : 시작 태그와 끝 태그 사이 내용물 건드리는 방법 
// ★ 문자열 읽기/쓰기(태그못넣음)
dom객체.innerText   
dom객체.textContent // 표준

// ★ 태그 같은거도 같이 넣기 
dom객체.innerHTML

// ※ 그냥 넣으면 덮어쓰기라서 기존거에 += 형식으로 넣는 경우가 많음 

event.target.classList.contains() // 이러면 해당 이벤트에 걸린 엘리먼트의 classList에 어떤 클래스가 포함되어 있는지 알 수 있다. 
event.target.classList.add() // 어떤 클래스를 포함시킬수 있다. 

```

### JavaScript로 CSS 건들이기

``` js
// DOM은 .style로 건들면 된다. 
const box = document.getElementById('box');
box.style.transform = 'rotate(45deg)';

//<div id="box" >상자</div> 이게 있을 때

const box =  document.getElementById('box');

// 이렇게 style을 입히는 건 편하다. 
box.style = 'font-size:5rem;'; // 가능
box.style['background-color'] = 'black'; // -가 들어가면 이렇게함
box.style.backgroundColor = 'blue';      // 캐멀표기법도 가능하다.

// 속성 재설정 > 이건 덮어쓰기다.
box.setAttribute('style', 'font-size:30px;'); //

// 스타일을 읽는건? 
// <div id="box" style="width:200px;"> 상자<div>
alert(box.style.width);  // ★★★ 인라인 스타일 시트가 없으면 못읽는다. 
// 인라인스타일 시트가 없는 경우엔 못 읽고, 인라인 스타일 시트가 이미 있으면 읽는다.

// 우리가 style을 입히는 작업할 때는 ★★ 인라인 스타일시트로 적용이 된다. 

// ★★★★ 인라인 시트가 없어도 실제 서식을 읽어오는 방식 
const list = window.getComputedStyle(box);
alert(list.getPropertyValue('width'));
// window.getComputedStyle(dom객체).getPropertyValue()
// 읽고나서 적용시에는 아래처럼 넣자. 
box.style.width = parseInt(list.getPropertyValue('width'))+50+'px';


```

### 마우스 좌표 가져오기
``` js

// <div id="box" class="box bg-yellow"></div>
// 위에 id="box" 가 있다고 가정 

let isDown = false;

    window.onmousedown = function() {
    // 0. event.screenX, event.screenY
    // 모니터 좌측 상단 기준의 좌표를 알려줌 쓰기 어려움

    // 이 안에서 event 객체로 clientX, clientY는
    // 1. 문서 좌측 상단 꼭지점이다. 
    // event.clientX, event.clientY
    
    // 2. 박스 안의 상대적 좌표
    // event.offsetX, event.offsetY
        if(event.target.id=='box'){ 
            isDown = true;
            x = event.offsetX; 
            y = event.offsetY; // 상자 내 눌린좌표가 된다.
        }
    }

    // 3. 드래그 할 때의 좌표 보정
    // 일반적으로 
    // box.style.left 
    // box.style.top 
    // 위와 같은 방식으로 지정해주는데 이것은 clientX, clientY를 기준으로 지정하는 경우에 좌측 상단 기준으로 문서 기준으로 
    // 찍은 지점으로 이동한다. 결과적으로 박스가 실체 찍은 지점의 위치가 아닌 좌측 상단으로 가서 위치가 더 움직인 상태라 보정 필요
    // 위에서 구한 x, y를 빼야함 
    window.onmousemove = function() {
            if(isDown) {
                box.style.left = event.clientX -x + 'px'; 
                box.style.top = event.clientY -y + 'px';
            }
    }

    window.onmouseup = function() {
            isDown = false; 
    }

    // 마우스 다운시 드래그 모드 on
    // 박스 드래그 > 해당 마우스 눌렸을 때 눌린 위치 기억
    // 마우스 움직일 때  계속 좌표 이동인데 offset 반영해서 이동
    // 마우스 업하면 드래그 모드 off 


    //돔객체.getBoundingClientRect()라는 함수가 있다.
    //해당 엘리먼트가 화면내에 어디있는지 알려주는 함수다.
    //getBoundingClientRect().left
    //getBoundingClientRect().top
    // ★ 근데 이함수에서 반환하는 값은 스크롤을 내릴 때마다 
    // top값이 바뀌니까 주의하자 


    // 스크롤이 이동된 만큼의 거리 
    // window.pageXOffset 
    // window.pageYOffset 
    // 이거도 스크롤 이동된거리다.
    //window.scrollX
    //window.scrollY

    event.keyCode 누른키       // > 키보드이벤트 때 사용 
    좌(37), 우(39)

    event.buttons             // > 마우스 이벤트 때 사용 
    왼쪽(1), 오른쪽(2), 왼쪽+오른쪾(3), 휠버튼(4)

    컨트롤키, 알트키, 쉬프트키  // 키보드 이벤인데 > 다른 종류의 키다.
    console.log(event.ctrlKey); 
    console.log(event.altKey);
    console.log(event.shiftKey);

```
### 타이머
```js
// setTimeout(), setInterval() 호출시 값을 반환한다. 
// 아이디 같은 타이머 번호다. 이것을 타이머를 식별함 
// 타이머 해제 할 때 이 번호를 넣어줌
// ★ setInterval()는 중복으로 호출될 수 있어서(빨라짐)
// 이것을 막아야 한다. if걸어서 막든가 

setTimeout()
setInterval()

clearTimeout(id)
claerInterval(id)

```
### 쓸만한 함수
``` js
isNaN(변수) : 숫자인지 검사해준다.
// NaN의 약자는 Not a Number
// ParseInt, ParseFloat, ParseDouble(X: 얘는 없다.)

txt = 'Hello~ Hong~ Bye~ Hong~';
console.log("before : "+ txt.replace('Hello', 'Hi'));
// 기본적으로 replace 함수는 한번만 치환해준다. 
// 그래서 정규식을 쓴다. g라는 말은 글로벌하게 바꿔줘! 
console.log("check : "+txt.replace(/Hong/g, 'Lee'));

conform() // 확인창 > 확인, 취소
prompt()  // 글자 입력창 > 인풋칸, 확인, 취소

// 타입 궁금할 때 
console.log(typeof n1);
// 노드이름 알아낼때 
console.log(list1.constructor.name, list2.constructor.name);


```
### template String
``` js
let name = '홍길동';
let age = 20;

// template String을 쓰지 않으면 뭔가 답답하다.
console.log('이름은 ' +name + '이고, 나이는 '+age+'살입니다.');

// ★ 역따옴표를 쓴다. 이거 쓰면 변수조작이 쉽다. 
let message = `이름은 ${name}이고, 나이는 ${age}살입니다. 만 나이로 ${age - 1}입니다. 현재 시각은 ${new Date()}입니다.`;

```

## 4. Jquery

``` js
// ★ 쓰기는 편한데 헷갈리다.

// DOM과 비교 
document.getElementById('txt1').value='값';

// 기본형 
jQuery('#txt1').val("jQuery");

jQuery > Alias > $

// 노드 접근은 
$('#box'),
$('.box'),
$('div:nth-child(odd)')

// ★ CSS 조작      
// css('속성')     > getter
// css('속성', 값) > setter

// 속성 변경 css에서 쓰던 속성명 그대로 쓰고 두번째 인자에 값 문자열 넘긴다.
$('#box').css('background-color', 'gold');


// 효과 
// 1.  hide(), show(), toggle(), slideUp(), slideDown(), slideToggle()
// 속도 : 인자로 slow, fast, 1000(숫자) 넣을 수 있다.

// 제이쿼리 애니메이션 
$('#box').animate({
width: 100,
height : '+=50px',
'margin-left' : '+=50px',
marginTop: '+=50px'
}); 
// key를 '' 붙여도 상관없다. 값은 px단위 붙이려면 ''붙이고 단위 없이 쓸거면 '' 없어도 된다. 

// 해당 엘리먼트에 class 속성을 추가
$('#box').addClass('one');
// 제거
$('#box').removeClass('two');
// 있으면 추가 없으면 제거 
$('#box').toggleClass('one');

// 콘텐츠 조작
// - val() > value 값을 이렇게 
// - text() > 내부 텍스트
// - html() > 내부 html 

// attr 조작      
// attr('속성')     > getter
// attr('속성', 값) > setter
// prop도 속성값 조작하는 메서드다.
// prop('name');
// prop('name', value);

// txt1은 인풋 태그
$('#txt1').attr({
    size : 50,
    maxlength: 10
}); // key value를 Object 형태로 넣을 수 있다. 

// 이렇게 하면 그냥 덮어쓰기 
$('#box').html('<img src="images/catty01.png">');

// 그래서 append나 prepend로 추가형식으로 넣음. 

// 부모.append(자식);   // 뒤쪽으로 push
// 부모.prepend(자식);  // 앞쪽으로 push

// 자식.appendTo(부모)
// 자식.prependTo(부모)

// ★★★ 다양한 활용법 ★★★
$('#box')
.append(`<img src="images/catty0${n}.png">`)
.css('border', '5px solid gold'); // 박스에다가 속성준다. 

// 내가 넣는 자식 엘리먼트에다가 속성 혹은 이벤트를 주면서 넣어준다. 
$('#box').append(
$(`<img src="images/catty0${n}.png">`)// 문자열을 제이쿼리로 감싸서 사용한다.
    .css('border', '5px solid black') // 추가되는 태그를 바로 조작 
    .click(function(){
        alert(this.src)
    })// 내가 추가한 이미지 + 스타일도 준다. 
);

$(`<img src="images/catty0${n}.png">`)
.css('border', '5px solid black')
.click(function(){
    // 여기서 this는 img임
    $(this).remove(); // 클릭된 본인 스스로 제거 
}).appendTo($('#box'));



$('#me').children().first()
$('#me').children().last()
//0, 1, 2
// -1 -2 -3 
$('#me').children().eq(-1).addClass('check');
// eq라는 함수로 자식 요소를 인덱스 기준으로 찾을 수 있다.indexOf느낌이다. 

$('#me').find('.item').addClass('check');
// ★ 자식요소를 셀렉터로 찾는다. 

$('#me').parent()

$('#me').prev()
$('#me').next()

$('#me').prevAll()
$('#me').nextAll()

$('#me').prevUntil('조건')

$('#me').siblings()

//형제 탐색
// previousSibling, nextSibling

// jQuery-ui가 제공하는 편의성 함수

draggable()
droppable()
dblclick()
selectable()

sortable() // 옮기기 가능
() 안쪽에 { }객체를 넣어서 속성지정 


 // 스크롤바의 위치?
// - DOM > window.scrollY
// - jQuery > scrollTop() > y  /x는 scrollLeft()

$(document).scroll(function(){
    // 스크롤 이벤트 처리
});


jquery.height() : 내부높이
jquery.innerHeight() : 내부높이 + padding
jquery.outerHeight() : 내부높이 + padding + border
jquery.outerHeight(true) : 내부높이 + padding + border + margin

```


## 5. 헷갈리는 거 ❓

### 문제 풀다가 발견한거 
``` js

```

### 이벤트 등록 방식

``` js

// 자바스크립트
// BOM 방식 > on이 붙음, 그리고 객체.이벤트
window.document.객체1.객체2.onclick = function() {};
window.document.객체1.객체2.onclick = f1;
function f1() {}

// DOM 방식 > addEventListner 방식은 on이 없다. 
const btn = document.getElementById('btn');
btn.addEventListner('click', function(){});

// DOM 방식 > getElement나 querySelector로 찾은 Dom 객체로 호출하는 방식 > on을 쓴다.
const btn = document.getElementById('btn');
btn.onclick = function(){};

// 제이쿼리
// 1. on 없는 방식
 jQuery('#btn3').click(function(){});
// 메서드 체이닝기법이 가능 

// 2. on붙이는 방식
jQuery('#btn4').on('mouseover', function(){
});

// 이벤트명에 '' 안붙여도 됨
jQuery('#btn4').on(mouseover,
 function(){
});

```

### 이벤트 제거방식
```js
// 자바스크립트
btn2.addEventListener('click', m1);
// 익명 함수보다는 지정함수로 이벤트 넣을 때


// 제이쿼리 
jQuery('#btn4').off('mouseout'); 
// 심플함 
```

### Arrow
``` js
※ 자바 람다식에선 -> 였다.
※ 자바 스크립트 Arrow는 => 이다. 
※ 익명함수다. 

const f2 = function(){
        console.log('f2');
};

// 위 표현을 아래 표현으로 > 함수명 없애고 () {} 사이에 '=>' 삽입 
const f3 = () => {
        console.log('f3');
};

// 실행문 1줄 > 블럭 생략
const f4 = () => console.log('f4');

// 매개변수 > 한개
const f5 = num => console.log(num);

// 매개변수가 2개 이상일 때 ( ) 생략불가
const f7 = (a, b) => console.log(a+b); 

// 반환값  > return 이랑 {  } 없애고 값만 달랑
const f8 = () => { return 100; }

const f9 = () => 200;

function test(){} // 일반 함수는 window를 객체의 프로퍼티 this를 기본적으로 갖는다. 만약에 이 함수로 이벤트를 등록하고 함수가 호출되면 this는 이벤트를 호출한 주체를 받는다. 

//★ 화살표함수는 이벤트를 등록하더라도
// 무조건 무조건 window를 참조한다. (*** 조심 !! )
// 그러면 이때 화살표함수를 쓰고 이벤트 호출 객체를 
// 참조하려면  alert(event.target); or alert(event.srcElement); 를 사용하자. 

```
### forEach
``` js

// forEach의 틀이 많이 헷갈림
// ★ {} 안에서는 ;쓸 수 있으나 {}을 생략하면 내부에서 ;을 못쓴다.
// ★ 이거 forEach( num => {} )
// () 안의 이름은 가명이다! 

// ★ 이거 forEach( (item, index) => {} )

const list = [ 5, 1, 9, 3, 7, 6, 8, 2, 4, 10];
list.forEach( num => {console.log(num)} );

// 인덱스까지 필요하면 매개변수를 하나 더쓴다. 
list.forEach( (item, index) => { console.log(item, index)} );

list.forEach( (item, index, origin) => {
    console.log(item, index, origin);
});

// ★ forEach 앞단에서 데이터를 가공하는 map()
list.map(num => n % 2 == 0? '짝':'홀').forEach(item => console.log(item));

// ★ forEach 앞단에서 데이터를 가공하는 filter() : 조건에 부합되는 요소만 찾는다.
list.filter( num => num > 5)
        .forEach(num => console.log(num));

// 배열 정렬메서드
list.sort();

// sort() 안에 배열 정렬기준 정의
console.log(list.sort((a, b) => a - b));

const mlist  = ['하길동', '아무개', '하하하', '호호호', '후후후'];


// find 함수를 정의한다. > 얘는 하나만 찾아준다. 뭘찾아줄지 ( )안에 정의 
console.log(mlist.find( name => name.startsWith('하')) ); // 


// jquery는 each라는 것을 제공하는데
// ★ index, item순으로 위의것과 반대이니 주의하자 
// jquery는 여러 엘리먼트가 발견되어 일괄처리가 된다. 
$('#tbl td').each((index, item) => {
    $(item).mouseover(function() {
        $(this).css('background-color','tomato');
    });
});// jquery 종류가 많다. 




```

### let, var

``` js
var는 재정의가 된다. > 사실은 변수의 개념이 아니라 속성의 개념이다. 

for(var i=0; i<5; i++){ }
console.log(i); // 이경우 i는 살아 있다. 
// 지역에서 선언됬는데? 왜? 

// let을 쓰면 이 문제는 해결 

★ 그냥 let써라 꼭 

```
  
### Loop 

  
``` js

var list = [10, 20, 30];
// 모양은 향상된 for문이나 변수는 인덱스가 출력 
for ( var n in list){
        console.log(n+','+list[n]); // 0 1 2 출력
}

// of 라는 키워드를 쓰면 변수가 값에 대입 
for ( var n of list){
        console.log(n); // 10, 20, 30 출력
}

```

### 이벤트 버블링 vs 터널링 
``` js
// 엘리먼트가 겹쳤을 때
// 어떤 엘리먼트에 이벤트를 걸면 그 엘리먼트가 구성하는 트리구조의 리프까지는 이벤트 전파가 된다. > 이벤트 터널링
// 이게 문제가 되는건 부모한테도 동일한 이벤트가 있을 떄가 문제임 
// 전파는 부모에서 자식 방향으로 된다. 

// 부모 ~ 자식순으로 Capture 진행 
// Capture phase > target phase > bubble phase 순으로 감 
// 실행의 시점의 브라우저 기본값은 bubble이다. 
// 만약에 capture면 최고 자식 클랙했는데 부모 먼저 실행되는게 이상함 

// 이벤트를 분명 하나에만 걸었어도 > 그 자식들도 이벤트가 걸려서 자식 클릭했더니 이벤트가 걸린다. 

// event.target.id 은 이벤트 전파로 인해 자식들에게 이벤트가 걸렸는데 이로 인해 이벤트 호출된 애의 id 가져온다. 
// event.currentTarget.id 이벤트 걸은 친구의 id 가져온다.
// this.id로 해도 됨 
event.target.
event.currentTarget.

// ★ 이벤트 버블링을 막기 위한 법

addEventListener의 두번째 인자조절> useCaputuring?
// 기본값 false > 버블링
// true > 캡쳐링 
event.cancelBubble = true;  // 비표준
event.stopPropagation();     // > 표준

// 이벤트 중단과 관련됨 ↓
//a. return false;
//b. event.preventDefault();

```

