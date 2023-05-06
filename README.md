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


// 콘텐츠 조작 : 시작 태그와 끝 태그 사이 내용물 건드리는 방법 
// ★ 문자열 읽기/쓰기(태그못넣음)
dom객체.innerText   
dom객체.textContent // 표준

// ★ 태그 같은거도 같이 넣기 
dom객체.innerHTML

// ※ 그냥 넣으면 덮어쓰기라서 기존거에 += 형식으로 넣는 경우가 많음 

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
    // 마우스 업하면 드래그 모드 해제 


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

### 이벤트 동작




### let, var

```
var는 재정의가 된다. > 사실은 변수의 개념이 아니라 속성의 개념이다. 

for(var i=0; i<5; i++){ }
console.log(i); // 이경우 i는 살아 있다. 
// 지역에서 선언됬는데? 왜? 

// let을 쓰면 이 문제는 해결 
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

