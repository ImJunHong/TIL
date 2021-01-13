# javascript의 배열 생성
* Array() 생성자 함수 또는 배열 리터럴 []을 사용하여 배열을 생성할 수 있음
* 배열 리터럴도 내부적으로는 Array() 생성자 함수를 사용하므로 기능의 차이는 없음
* Array()의 인자로 Number 타입을 받으면 해당 인자와 같은 크기의 빈 배열을 생성하고, Number 타입이 아니면 해당 인자를 첫 번째 요소로 하는 배열을 생성함

```javascript
const a = new Array(2); // 크기가 2인 빈 배열 생성
const b = new Array("2"); // ["2"]
const c = new Array(2.5); // Uncaught RangeError: Invalid array length (정수가 아닌 Number 타입을 인자로 받으면 RangeError 발생)
```
