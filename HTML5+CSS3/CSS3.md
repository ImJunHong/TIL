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

# display:none과 visibility:hidden의 차이
* 둘 다 해당 스타일을 가진 태그를 보이지 않게 함
* display:none은 공간을 할당하지 않으나, visibility:hidden은 공간을 할당함

# float를 clear시키는 방법
* float 속성이 있는 블록 요소는 주변의 다른 요소들의 배치에 영향을 미침
* clear 속성은 float 속성이 다른 요소들의 배치에 영향을 미치지 않도록 해제시키는 역할을 함
```html
<body>
  <div id="container">
    <div>div div 1</div>
    <div>div div 2</div>
  </div>
  <div id="clear">div 3</div>
</body>
```
## 1. float를 clear시키지 않았을 때
```css
#clear {
  background-color : pink;
}
div div {
  background-color : red;
  float : left;
}
```
<img src="https://user-images.githubusercontent.com/67459853/104121305-7348c400-5380-11eb-998a-9a53c14353fb.PNG">

## 2. float를 clear시켰을 때
```css
#clear {
  background-color : pink;
}
div div {
  background-color : red;
  float : left;
}
#container::after {
  display : block;
  content : "";
  clear : both;
}
```
<img src="https://user-images.githubusercontent.com/67459853/104121307-7479f100-5380-11eb-81f2-fa833eae716c.PNG">

::after는 가상 요소(Pseudo-Element)로 해당 요소의 맨 마지막 자식으로 의사(pseudo) 요소를 생성한다. 위의 코드에서는 부모 요소인 clearfix 뒤에 보이지 않는 의사 요소를 만들어 뒤에 있는 요소가 위로 따라 올라가지 않도록 함

# @import와 link의 차이
## @import
```css
@import url(mystyle.css); /* @import url('mystyle.css'); 또는 @import "mystyle.css";도 가능 */
```
* <style> 안에서만 사용되며, 그렇기 때문에 CSS 파일 내부에서도 @import를 사용할 수 있음
* 직렬방식으로 다운로드하여 로딩 속도가 비교적 긺.
* 여러 개의 @import 사용시 일부 브라우저(IE)에서 다운로드 순서가 달라 문제가 발생할 수 있음
* 일부 브라우저(Microsoft Edge)에서 @import 방식을 처리하지 못함

## link
```html
<head>
  <link href="mystyle.css" type="text/css" rel="stylesheet">
</head>
```
* type="text/css"는 불러오는 파일이 CSS 언어로 작성된 텍스트 파일임을 알려줌
* rel="stylesheet"는 불러오는 파일이 스타일 시트임을 알려줌
* 종료 태그(\</link\>)가 없음
* 병렬방식으로 다운로드하여 로딩 속도가 비교적 빠름
* 여러 개의 link를 사용해도 IE에서 동일한 순서로 작동함
* Edge에서도 처리가 가능한 방식임

# Vendor Prefix
* 아직 CSS 표준으로 인정되지 않은 실험적이고 비표준인 속성에 각 브라우저 제작사별로 별개의 접두어를 붙임
* -webkit- : 웹킷 계열 브라우저(사파리, 크롬)
* -moz- : 모질라(파이어폭스)
* -o- : 오페라
* -ms- : 마이크로소프트(인터넷 익스플로러, 마이크로소프트 엣지)
* 접두어가 붙은 속성은 해당 버전의 브라우저에서 적용되고 다른 브라우저에서는 무시됨
* 접두어가 붙은 속성을 모두 작성한 후에 기본속성으로 작성해야만 접두어가 붙은 속성이 정상적으로 적용됨
```css
-webkit-box-sizing: border-box;
-moz-box-sizing: border-box;
box-sizing: border-box;
```
