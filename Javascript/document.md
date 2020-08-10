# document.write()과 document.writeln()의 차이

둘 다 자바스크립트 코드로 HTML 콘텐츠를 웹 페이지에 직접 삽입하여 출력되게 함.

document.writeln()은 텍스트에 '\n'을 덧붙여 출력한다.

또한 \<pre\>태그를 사용했을 때, document.writeln()을 사용하면 자동으로 줄바꿈이 일어난다.

```html
<script>
document.write("hello");
document.write("world");
</script>

<pre>
<script>
document.write("hello");
document.write("world");
</script>
</pre>
```
```bash
helloworld
helloworld
```

```html
<script>
document.writeln("hello");
document.writeln("world");
</script>

<pre>
<script>
document.writeln("hello");
document.writeln("world");
</script>
</pre>
```
```bash
hello world
hello
world
```
