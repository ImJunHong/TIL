# document.getElement\*와 document.querySelector\*의 차이
* getElementById(id)는 문자열 id와 일치하는 id속성을 가진 요소를 반환하고, querySelector(selectors)는 selectors와 일치하는 가장 첫 번째 요소를 반환함
* 둘 다 일치하는 요소가 없으면 null 반환
```html
<div id="element">찾고자 하는 요소</div>
```
```javascript
// elemById와 elemBySelector는 같은 객체를 가리킴
const elemById = document.getElementById("element");
const elemBySelector = document.querySelector("#element");
console.log(elemById === elemBySelector); // true
```

* getElementsByClassName(names)는 names에 주어진 클래스와 일치하는 클래스를 가진 모든 요소를 HTMLCollection으로 반환함
* querySelectorAll(selectors) selectors와 일치하는 모든 요소를 NodeList로 반환함
```html
<div class="myClass">찾고자 하는 요소</div>
```
```javascript
const collection = document.getElementsByClassName("myClass");
const nodeList = document.querySelectorAll(".myClass");
console.log(collection === nodeList); // false

// querySelector(selectors)는 querySelectorAll(selectors)[0]과 같음
console.log(document.querySelector(".myClass") === nodeList[0]); // true
```

# document.write()과 document.writeln()의 차이

둘 다 자바스크립트 코드로 HTML 콘텐츠를 웹 페이지에 직접 삽입하여 출력되게 함.

document.writeln()은 텍스트에 '\n'을 덧붙여 출력한다.

또한 \<pre\>태그를 사용했을 때, document.writeln()을 사용하면 자동으로 줄바꿈이 일어난다.

```html
<script>
document.write("hello");
document.write("world");
</script>

<pre>
<script>
document.write("hello");
document.write("world");
</script>
</pre>
```
```bash
helloworld
helloworld
```

```html
<script>
document.writeln("hello");
document.writeln("world");
</script>

<pre>
<script>
document.writeln("hello");
document.writeln("world");
</script>
</pre>
```
```bash
hello world
hello
world
```
