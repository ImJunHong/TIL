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

* 그라데이션 효과
```javascript
// 선형 그라데이션 지정(x1, y1, x2, y2)
let gradation = context.createLinearGradient(0, 0, 250, 250);
gradation.addColorStop(0, "red");
gradation.addColorStop(0.5, "orange");
gradation.addColorStop(1, "yellow");
context.fillStyle = gradation;
context.fillRect(0, 0, 250, 250);

gradation = context.createLinearGradient(250, 125, 500, 125);
gradation.addColorStop(0, "red");
gradation.addColorStop(0.5, "orange");
gradation.addColorStop(1, "yellow");
context.fillStyle = gradation;
context.fillRect(250, 0, 500, 250);

// 원형 그라데이션 지정(x1, y1, radius1, x2, y2, radius2)
gradation = context.createRadialGradient(125, 375, 50, 125, 375, 125);
gradation.addColorStop(0, "red");
gradation.addColorStop(0.5, "orange");
gradation.addColorStop(1, "yellow");
context.fillStyle = gradation;
context.beginPath();
context.arc(125, 375, 125, 0, Math.PI*2);
context.fill();

gradation = context.createRadialGradient(375, 375, 125, 250, 250, 50);
gradation.addColorStop(0, "red");
gradation.addColorStop(0.5, "orange");
gradation.addColorStop(1, "yellow");
context.fillStyle = gradation;
context.beginPath();
context.arc(375, 375, 125, 0, Math.PI*2);
context.fill();
```
<img src="https://user-images.githubusercontent.com/67459853/107852948-d386c600-6e56-11eb-8c6e-07be06bed9c9.PNG">

* 그림자 효과
```javascript
context.shadowColor = "black"; // 그림자 색깔 지정
context.shadowOffsetX = 10; // 그림자의 가로 위치 지정
context.shadowOffsetY = 10; // 그림자의 세로 위치 지정
context.shadowBlur = 8; // 그림자의 흐림 정도 지정
context.fillStyle = "orange";
context.fillRect(0, 0, 250, 250);
```
<img src="https://user-images.githubusercontent.com/67459853/107877571-9ed74500-6f10-11eb-89eb-2f57de754d81.PNG">

* artTo(x1, y1, x2, y2, radius)
  * 두 직선 사이의 호를 그릴 때 사용 (두 직선이 평행하지 않아야 함)
  * 주로 곡선 모서리를 만드는데 활용됨
  * 현재 경로의 가장 마지막 점(x0, y0)과 (x1, y1)을 잇는 직선, (x1, y1)과 (x2, y2)를 잇는 직선 사이에 내접하는 원을 잇는 모양을 그림
```javascript
context.beginPath();
context.moveTo(150, 150); // 경로의 가장 마지막 점이 존재해야 하므로, moveTo로 x0, y0 지정
context.arcTo(150, 350, 350, 350, 50);
context.lineTo(350, 350);
context.stroke();
```
<img src="https://user-images.githubusercontent.com/67459853/107961197-e9c48b80-6fe8-11eb-924a-74cbc2c04a92.PNG">

* quadraticCurveTo(cpx, cpy, x, y)
  * 2차 베지에 곡선을 그릴 때 사용
  * 현재 경로의 가장 마지막 점이 시작점, (x, y)가 종료점이며, (cpx, cpy)가 조절점임
```javascript
context.lineWidth = 5;
context.strokeStyle = "black";
context.beginPath();
context.moveTo(150, 150);
context.quadraticCurveTo(200, 350, 250, 150);
context.stroke();

// 시작점, 종료점, 조절점 표시를 위한 부분
function drawLine(x1, y1, x2, y2) {
    context.lineWidth = 3;
    context.strokeStyle = "grey";
    context.beginPath();
    context.moveTo(x1, y1);
    context.lineTo(x2, y2);
    context.stroke();
}

function drawPoint(x, y, color) {
    context.beginPath();
    context.arc(x, y, 5, 0, 2*Math.PI);
    context.fillStyle = color;
    context.fill();
}

drawLine(150, 150, 200, 350);
drawLine(250, 150, 200, 350);
drawPoint(150, 150, "red"); // 시작점
drawPoint(250, 150, "red"); // 종료점
drawPoint(200, 350, "blue"); // 조절점
```
<img src="https://user-images.githubusercontent.com/67459853/108065506-75015800-70a1-11eb-976d-1956ba8b93a4.PNG">
<img src="https://user-images.githubusercontent.com/67459853/108065509-7599ee80-70a1-11eb-984e-5b85c0e48d8a.PNG">

* bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
  * 3차 베지에 곡선을 그릴 때 사용
  * 현재 경로의 가장 마지막 점이 시작점, (x, y)가 종료점이며, (cp1x, cp1y)와 (cp2x, cp2y)는 조절점임
```javascript
context.lineWidth = 5;
context.strokeStyle = "black";
context.beginPath();
context.moveTo(150, 250);
context.bezierCurveTo(200, 150, 300, 150, 350, 250);
context.stroke();

// 시작점, 종료점, 조절점 표시를 위한 부분(drawLine, drawPoint는 위에 quadraticCurveTo 예시에 정의해 놓음)
drawLine(150, 250, 200, 150);
drawLine(350, 250, 300, 150);
drawPoint(150, 250, "red");
drawPoint(350, 250, "red");
drawPoint(200, 150, "blue");
drawPoint(300, 150, "blue");
```
<img src="https://user-images.githubusercontent.com/67459853/108065511-76328500-70a1-11eb-8e0a-3b5add82248d.PNG">
<img src="https://user-images.githubusercontent.com/67459853/108065510-76328500-70a1-11eb-9e8c-0158307999f3.PNG">
