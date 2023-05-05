# basicFrontend

## 복습용 README.md 


## 1. HTML 
``` js
// <table> 만들어 놓으면 중간에 tbody 껴있음
// 이거 고려하고 탐색
// <table> tbody <tr> <td>
```

## 2. CSS


## 3. Javascript

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

```
### 마우스 좌표 가져오기


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




  
  
  

