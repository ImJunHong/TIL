# attr(attribute-name)
* HTML 태그의 속성값을 반환
```html
<div id="box"></div>
```
```css
#box {
    width: 50px; height: 50px;
    background-color: mistyrose;
}
#box:after {
    content: '123'attr(id)'abc';
}
```
<img src="https://user-images.githubusercontent.com/67459853/110311852-b3a68480-8047-11eb-9d97-d1c9f6ab1903.PNG">

# gradient
## linear-gradient()
* 선형 그라데이션
* background 속성에 사용(background-color에 사용하면 작동하지 않음)
```html
<div id="box"></div>
```
```css
#box {
    width: 200px; height: 150px;
    background: linear-gradient(pink, deepskyblue);
}
```
<img src="https://user-images.githubusercontent.com/67459853/110318568-fb7dd980-8050-11eb-9422-cddd2d0e441b.PNG">

```css
#box {background: linear-gradient(45deg, pink, deepskyblue);}
```
<img src="https://user-images.githubusercontent.com/67459853/110318567-fae54300-8050-11eb-87d8-98c5ac28c304.PNG">

```css
/* linear-gradient(90deg, pink, deepskyblue)와 동일 */
#box {background: linear-gradient(to right, pink, deepskyblue);}
```
<img src="https://user-images.githubusercontent.com/67459853/110318563-fa4cac80-8050-11eb-8fbb-119bcbc120f6.PNG">

```css
/* linear-gradient(pink 0%, lightgreen 50%, deepskyblue 100%)와 동일 */
#box {background: linear-gradient(pink, lightgreen 50%, deepskyblue);}
```
<img src="https://user-images.githubusercontent.com/67459853/110318575-fc167000-8050-11eb-9a3a-3269157ddfd7.PNG">

```css
/* linear-gradient(pink 0% 33%, lightgreen 33% 66%, deepskyblue 66% 100%)와 동일 */
#box {background: linear-gradient(pink 33%, lightgreen 33% 66%, deepskyblue 66%);}
```
<img src="https://user-images.githubusercontent.com/67459853/110318573-fc167000-8050-11eb-9187-c58f41339bb0.PNG">

```css
/* linear-gradient를 중첩하여 사용 가능. 이 때 alpha가 1이면 가장 먼저 적용한 linear-gradient만 보임 */
#box {
    background: linear-gradient(45deg, rgba(255, 0, 0, 0.75), rgba(0, 0, 0, 0) 75%),
                linear-gradient(105deg, rgba(0, 255, 0, 0.75), rgba(0, 0, 0, 0) 75%),
                linear-gradient(165deg, rgba(0, 0, 255, 0.75), rgba(0, 0, 0, 0) 75%),
                linear-gradient(225deg, rgba(255, 255, 0, 0.75), rgba(0, 0, 0, 0) 75%),
                linear-gradient(285deg, rgba(255, 0, 255, 0.75), rgba(0, 0, 0, 0) 75%),
                linear-gradient(345deg, rgba(0, 255, 255, 0.75), rgba(0, 0, 0, 0) 75%);
}
```
<img src="https://user-images.githubusercontent.com/67459853/110318570-fb7dd980-8050-11eb-9b45-79d48f3c1fe5.PNG">
