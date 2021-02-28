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
