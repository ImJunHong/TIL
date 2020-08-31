# 이벤트 리스너 등록
## 1. HTML 태그에 속성으로 등록
* 리스너 코드가 짧은 경우에 적합
* 가독성이 좋지 않으며, 유지보수가 힘들어질 수 있음

```html
<p ondblclick="this.style.backgroundColor='yellow'">
더블클릭하면 배경색을 노란색으로 변경
</p>
```

## 2. DOM 객체의 이벤트 리스너 프로퍼티에 등록
* 하나의 이벤트 타입에 하나의 이벤트 리스너 등록 가능

```javascript
window.onload = function() {
    const text = document.getElementById("text");
    text.style.backgroundColor = "yellow";
}
```
```javascript
function load() {
    const text = document.getElementById("text");
    text.style.backgroundColor = "yellow";
}
window.onload = load;
```

## 3. DOM 객체의 addEventListener() 메소드를 이용하여 등록
* addEventListener(eventName, listener[, useCapture])
  * eventName : 이벤트 타입을 문자열로 전달
  * listener : 이벤트 리스너로 등록할 함수 이름
  * useCapture : true면 캡처링 방식으로, false면 버블링 방식으로 이벤트 전파. 기본값은 false
  * 동일한 이벤트에 대해 여러 개의 리스너를 중복 등록할 수 있음
  * 표준 브라우저(IE9 이상, 파이어폭스, 오페라, 사파리, 크롬)에서 지원
 
```javascript
const text = document.getElementById("text");
text.addEventListener("click", func1);
text.addEventListener("click", func2);

function func1() {
    text.style.backgroundColor = "yellow";
}

function func2() {
    text.style.fontSize = "20px";
}
```

## 4. DOM 객체의 attachEvent() 메소드를 이용하여 등록
* attachEvent(eventName, listener)
    * eventName : 이벤트 타입을 문자열로 전달. addEventListener()와 달리 이벤트 타입 앞에 on을 붙여야 함
    * listener : 이벤트 리스너로 등록할 함수 이름
    * IE8 이하, 오페라 등의 브라우저에서 지원
    
```javascript
const text = document.getElementById("text");
text.attachEvent("onclick", func1);

function func1() {
    text.style.backgroundColor = "yellow";
}
```

# 이벤트 객체 전달받기
* 이벤트 객체는 이벤트 리스너 함수(이벤트 핸들러)의 첫 번째 매개변수로 전달
* 이벤트 리스너 함수 선언시 이벤트 객체를 전달받을 첫 번째 매개변수를 명시적으로 선언하여야 함(예시의 e 대신 다른 이름 가능)
* HTML 태그에서 이벤트 리스너를 만들 때는 이벤트 객체를 반드시 `event`라는 이름으로 전달해야 한다.

```javascript
const button = document.getElementById("button");
button.onclick = change;

function change(e) {
    e.target.style.backgroundColor = "yellow";
}
```
```javascript
// 익명 함수일 때
const button = document.getElementById("button");
button.onclick = function(e) {
    e.target.style.backgroundColor = "yellow";
}
```
```html
<!--HTML 태그에 이벤트 리스너를 만들 때-->
<button onclick="change(event)">색 변경</button>
<script>
function change(e) {
    e.target.style.backgroundColor = "yellow";
}  
</script>
```
* HTML 태그에 직접 이벤트 리스너를 연결하는 것은 유지보수에 좋지 않아 권장되지 않음(HTML과 javascript는 분리할 것!)
