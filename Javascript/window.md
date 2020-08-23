# window.open(URL[, windowName][, feature])
* URL : 윈도우에 출력할 웹 페이지 주소. 생략시 빈 윈도우 출력(""나 null을 입력해도 동일)
* windowName : 윈도우 이름 전달
  * _blank : windowName의 기본값이며, 이름이 없는 새 윈도우에 웹 페이지 출력
  * _parent : 윈도우를 새로 열지 않고, 현재 윈도우의 부모 윈도우에 웹 페이지 출력
  * _self : 현재 윈도우에 웹 페이지 출력
  * _top : 최상위 브라우저 윈도우에 웹 페이지 출력
  * 이 외에 임의로 정한 이름을 사용하면, 해당 이름을 가진 새 윈도우에 웹 페이지를 출력함
  * 동일한 이름에서 open()하면 새 윈도우가 아닌 동일한 이름의 기존 윈도우에서 웹 페이지를 출력함
* feature : 윈도우의 모양이나 크기 등의 속성 전달
  * width, height, left, top 등의 속성은 정수를 값으로 받음
  * resizable, location, menubar, scrollbars, status, toolbar 등의 속성은 no/yes(0/1)를 값으로 받음
* HTML태그나 DOM 객체에서 window를 생략하고 open()만 호출하면 document.open()으로 처리됨

```javascript
window.open("https://github.com/ImJunHong", "myGit", "width=600,height=400,resizable=1,toolbar=no");
```
