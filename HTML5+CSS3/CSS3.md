# @import와 link의 차이
## @import
```css
<style>
  @import url(mystyle.css); /* @import url('mystyle.css'); 또는 @import "mystyle.css";도 가능 */
</style>
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
* 종료 태그(</link>)가 없음
* 병렬방식으로 다운로드하여 로딩 속도가 비교적 빠름
* 여러 개의 link를 사용해도 IE에서 동일한 순서로 작동함
* Edge에서도 처리가 가능한 방식임
