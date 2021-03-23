# 변수 선언
* :root 가상 클래스 내부에 "--변수명: 값;"의 형태로 선언
* :root는 문서 내 최상의 요소를 가리키며, html과 같음
* 그럼에도 불구하고 :root을 쓰는 이유는 CSS 명시도 점수가 더 높기 때문
  (태그 선택자인 html은 1점, 가상 클래스인 :root는 10점)
```css
:root {--green: #35dc8e;}
```
# 변수 사용
* "var(변수명)"의 형태로 사용
```css
#box {
    background-color: var(--green);
}
```
