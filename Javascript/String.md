# String.slice(idxA[,idxB])와 String.substring(idxA[,idxB])의 차이
* ### 공통점
  * idxA에서 idxB 바로 앞까지의 문자열을 복사하여 반환
  * idxB가 생략되면 idxA에서 끝까지의 문자열을 복사하여 반환
  * idxA와 idxB가 같으면 empty string 반환
  * idxA와 idxB 둘 중 하나가 string의 length보다 크면 string의 length로 대체

* ### 차이점
  ### String.slice()
  * idxA가 idxB보다 크면 empty string 반환
  * idxA가 음수면 idxB도 음수여야 한다. 그렇지 않으면 empty string 반환
  ### String.substring()
  * 음수이거나 NaN인 index는 0으로 대체
  * idxA가 idxB보다 크면 서로 자리를 바꿈

```javascript
const str = "0123456789"

const slice1 = str.slice(3,5);
const sub1 = str.substring(3,5);
const slice2 = str.slice(3,-5);
const sub2 = str.substring(3,-5);
const slice3 = str.slice(-3,5);
const sub3 = str.substring(-3,5);
const slice4 = str.slice(-5);
const sub4 = str.substring(-5);

console.log("str.slice(3,5) : " + slice1);
console.log("str.substring(3,5) : " + sub1);
console.log("str.slice(3,-5) : " + slice2);
console.log("str.substring(3,-5) : " + sub2);
console.log("str.slice(-3,5) : " + slice3);
console.log("str.substring(-3,5) : " + sub3);
console.log("str.slice(-5) : " + slice4);
console.log("str.substring(-5) : " + sub4);
```
```bash
str.slice(3,5) : 34
str.substring(3,5) : 34
str.slice(3,-5) : 34
str.substring(3,-5) : 012  #(3,-5) → (3,0) → (0,3)
str.slice(-3,5) : 
str.substring(-3,5) : 01234 #(-3,5) → (0,5)
str.slice(-5) : 56789
str.substring(-5) : 0123456789 #(-5) → (0)
```
