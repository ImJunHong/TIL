# Element.dataset
* 사용자 지정 데이터 속성(data-\*)에 대한 읽기 전용 DOMStringMap 반환
* 접두사 data-는 삭제되며, dash-style 이름은 camelCase로 변환됨
* Element.dataset.keyname 또는 Element.dataset[keyname]으로 사용자 지정 데이터 속성에 접근 가능

# DOM 객체의 CSS3 스타일 프로퍼티 읽기
## Element.style
* DOM 객체의 style 속성 참조를 통해 CSS 스타일 프로퍼티에 접근할 수 있음
```javascript
const element = document.getElementById("elementId");
const color = element.style.color;
```
* style을 변경할 수 있음
```javascript
element.style.color = "red";
```
* HTML 태그 내에 인라인 방식으로 지정된 CSS 스타일에만 접근할 수 있음
```css
#elementId02 {color : red;}
```
```html
<div id="elementId01" style="color:black"></div>
<div id="elementId02"></div>
```
```javascript
const color01 = document.getElementById("elementId01").style.color; // black
const color02 = document.getElementById("elementId02").style.color; // ""
```

## window.getComputedStyle(Element)
* Element에 적용된 모든 CSS 속성 값을 담고 있는 객체를 반환
```javascript
const color = window.getComputedStyle(element).color; // rbg값으로 색상 반환
```
* 읽기 전용이기 때문에 style을 변경할 수 없음
```javascript
window.getComputedStyle(element).color = "rgb(0,0,0)"; // Uncaught DOMException: Failed to set the 'color' property on 'CSSStyleDeclaration': These styles are computed, and therefore the 'color' property is read-only.
```
