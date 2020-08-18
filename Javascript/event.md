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
    var text = document.getElementById("text");
    text.style.backgroundColor = "yellow";
}
```
```javascript
function load() {
    var text = document.getElementById("text");
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
 
```javascript
text = document.getElementById("text");
text.addEventListener("click", func1);
text.addEventListener("click", func2);

function func1() {
    text.style.backgroundColor = "yellow";
}

function func2() {
    text.style.fontSize = "20px";
}
```
