# \<dl\>
* \<dl\>은 개념-정의를 나타내는 목록
* \<dt\>, \<dd\>를 자식으로 가짐
  * \<dt\>는 개념을 나타내는 인라인 요소
  * \<dd\>는 정의를 나타내는 블럭 요소
  * \<dt\>, \<dd\>는 \<dl\> 밖에서 독립적으로 사용할 수 없음
  * \<dt\>, \<dd\>는 반드시 하나의 짝으로 이루어질 필요는 없음(하나의 \<dt\>에 여러 \<dd\>를 가질 수 있음, 연속적인 \<dt\> 가능)

# \<input type="submit"\>과 \<button\>\</button\> 비교
* button 태그의 디폴트 type은 submit임. type 속성을 명시하지 않으면 submit 기능을 수행함
* button은 input과는 달리 \<button\>\</button\> 사이에 컨텐츠를 삽입할 수 있는 등 UI 디자인에서의 활용도가 높음

# \<meta name="viewport" content="width=device-width, initial-scale=1.0"\>
* 사용중인 디바이스에 따라 해상도가 바뀌는 반응형 웹을 만들때 사용
* content 속성
  * width/height: 화면의 너비/높이
  * initial-scale: 초기 확대 비율
  * user-scalable: 확대 및 축소 가능 여부
  * minimum-scale: 최소 축소 비율
  * maximum-scale: 최대 축소 비율

# \<source\>\</source\>
* \<audio\>태그나 \<video\>태그 내부에 삽입하여 음성이나 영상 파일을 불러옴
* \<audio\>, \<video\>태그의 src속성을 생략하고 대신 \<source\>태그의 src속성에 경로를 입력하면 됨
* 복수의 \<source\>태그를 삽입하면 그 중에서 가장 첫 번째로 브라우저가 지원하는 파일을 재생함
```html
<audio controls>
    <source src="audio01.ogg" type="audio/ogg">
    <source src="audio01.wav" type="audio/wav">
    audio 태그를 지원하지 않는 브라우저입니다.
</audio>
```

# data-\*(사용자 지정 데이터 특성)
* data-속성으로 HTML에 데이터를 저장할 수 있음
* JavaScript에서 DOM 객체의 <a href="https://github.com/ImJunHong/TIL/blob/master/Javascript/DOM.md#elementdataset">dataset</a> 속성을 통해 사용자 지정 data-속성 값에 접근할 수 있음
```html
<div data-color="mistyrose" data-width="100"></div>
<div data-color="lightgreen" data-width="100"></div>
<div data-color="skyblue" data-width="100"></div>
```
```javascript
const elems = document.getElementsByTagName("div");
for(let i=0; i<elems.length; i++) {
    elems[i].style.backgroundColor = elems[i].dataset.color;
    elems[i].innerHTML = elems[i].style.width = elems[i].dataset.width + "px";
}
```
<img src="https://user-images.githubusercontent.com/67459853/110214372-a1153980-7ee7-11eb-8996-4282d86a0e71.PNG">
