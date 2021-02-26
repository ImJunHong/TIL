# box-sizing
* 박스의 크기를 결정하는 기준을 지정
## context-box
* 디폴트 값
* 크기(width, height)를 content 영역을 기준으로 지정(padding, border, margin을 포함하지 않음)
## border-box
* 크기를 border를 기준으로 지정(=content+padding+border, margin은 포함하지 않음)
* padding과 border를 추가하면 content 영역이 줄어들면서 크기를 유지함

```css
display: inline-block;
background-color: mistyrose;
box-sizing: content-box;
width: 200px;
height: 200px;
padding: 20px;
border: 10px solid black;
```
```css
display: inline-block;
background-color: aliceblue;
box-sizing: border-box;
width: 200px;
height: 200px;
padding: 20px;
border: 10px solid black;
```
<img src="https://user-images.githubusercontent.com/67459853/107148072-9c1aa400-6994-11eb-96c1-1d05eeeb893c.PNG">

# position
## 자손의 position 속성에 absolute를 적용할 때
* 부모에 height 속성을 사용해서 자리를 차지하도록 해야 함
* 부모의 position 속성에 relative를 적용하여 자손이 부모를 기준으로 위치를 지정하도록 해야 함
```html
<div class="line"></div>
    <div id="wrapper">
        <div id="box1"></div>
        <div id="box2"></div>
    </div>
<div class="line"></div>
```
```css
.line {
    background-color: black;
    height: 30px;
}
#wrapper {
    position: relative;
    height: 100px;
    border: 3px solid red;
}
#box1 {
    position: absolute;
    width: 50px;
    height: 50px;
    left: 0;
    top: 0;
    background-color: green;
}
#box2 {
    position: absolute;
    width: 50px;
    height: 50px;
    left: 25px;
    top: 25px;
    background-color: blue;
}
```
<img src="https://user-images.githubusercontent.com/67459853/109302873-3b88d380-787d-11eb-9109-6425a9b92bc4.PNG">

* 부모의 height 속성이 없을 때
```css
#wrapper {
    position: relative;
    /*height: 100px;*/
    border: 3px solid red;
}
```
<img src="https://user-images.githubusercontent.com/67459853/109302871-3af03d00-787d-11eb-81c3-5ee7d0505b9b.PNG">

* 부모의 position 속성이 기본값(static)일 때
```css
#wrapper {
    /*position: relative;*/
    height: 100px;
    border: 3px solid red;
}
```
<img src="https://user-images.githubusercontent.com/67459853/109303955-dafa9600-787e-11eb-9222-2b9a306dba82.PNG">
