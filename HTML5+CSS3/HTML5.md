# \<canvas\>\</canvas\>
* 웹 페이지에서 자바스크립트를 통해 그래픽 작업을 수행할 수 있음
* 캔버스 객체로부터 렌더링 컨텍스트를 얻어내어 제공되는 메소드로 그림을 그릴 수 있음
```html
<canvas id="canvas" width="300", height="300"></canvas>
```
```javascript
const canvas = document.getElementById("canvas");
const context = canvas.getContext("2d"); //CanvasRenderingContext2D
```
## CanvasRenderingContext2D로 그림 그리기
* 경로(path)를 통해 그리기
```javascript
context.beginPath(); // 이전 경로를 모두 지우고 빈 경로를 시작
context.strokeStyle = "red"; // 선 색 설정
context.fillStyle = "green"; // 채우기 색 설정
context.moveTo(50, 50); // 새로운 점을 경로에 추가
context.lineTo(75, 75); // 가장 마지막에 경로에 추가된 점과 해당 좌표의 점을 잇는 선 추가
context.lineTo(100, 25);
context.closePath(); // 경로의 시작점과 끝 점을 잇는 선을 추가하고 경로를 닫음
context.stroke(); // 경로 내에 존재하는 모든 도형의 외곽선을 캔버스에 그림

context.beginPath();
context.rect(150, 50, 25, 25); // 경로에 사각형 추가(x, y, 너비, 높이)
context.fill(); // 경로 내에 만들어진 모든 도형(닫힌 영역)의 내부를 색으로 채워 캔버스에 그림

context.beginPath();
context.arc(50, 150, 25, 0, 1.5*Math.PI, false); // 경로에 원호 추가(x, y, 반지름, 시작각도, 끝각도, 방향(생략가능, 디폴트:false(시계방향))
context.stroke();
```
<img src="https://user-images.githubusercontent.com/67459853/106387862-13918600-641f-11eb-992d-cf82322d3699.PNG">

* 경로를 거치지 않고 캔버스에 직접 그리기
```javascript
context.strokeStyle = "red";
context.fillStyle = "green";
context.strokeRect(50, 50, 25, 25); // 사각형의 외곽선을 캔버스에 직접 그림
context.fillRect(100, 50, 25, 25); // 사각형의 내부를 색으로 채워 캔버스에 직접 그림

context.font = "italic 25px arial"; // 폰트 설정
context.strokeText("abc", 50, 150); // 텍스트의 외곽선을 캔버스에 직접 그림
context.fillText("가나다", 150, 150); // 텍스트의 내부를 색으로 채워 캔버스에 직접 그림
```
<img src="https://user-images.githubusercontent.com/67459853/106388009-e5f90c80-641f-11eb-8f8e-31798e5511e2.PNG">

* 캔버스 지우기
```javascript
context.clearRect(0, 0, canvas.width, canvas.height); // 해당 사각형의 범위 안에 있는 그림을 지움
```

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
 
