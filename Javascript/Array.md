# Array.prototype.map(callback(currentValue[, index[, array]])[, thisArg])
* 배열의 모든 요소에 대하여 callback함수를 호출한 반환값을 모아 새로운 배열을 반환함
* 두 번째 인수로 callback함수의 this에 바인딩할 값을 지정함
```javascript
function triple(x) {
    return x * 3;
}
console.log([1, 2, 3, 4, 5].map(triple)); // [3, 6, 9, 12, 15]
```
* 만약 callback함수가 두 개 이상의 매개변수를 갖는다면, 첫 번째 인수로 배열의 요소, 두 번째 인수로 요소의 index, 세 번째 인수로 전체 배열을 받게 됨
```javascript
console.log(["1", "2", "3", "4", "5"].map(parseInt)); // [1, NaN, NaN, NaN, NaN]
// 위 코드에서 반환된 배열은 아래와 같은 과정을 거쳐 반환됨
// console.log(parseInt("1", 0, ["1", "2", "3", "4", "5"])); // 1
// console.log(parseInt("2", 1, ["1", "2", "3", "4", "5"])); // NaN
// console.log(parseInt("3", 2, ["1", "2", "3", "4", "5"])); // NaN
// console.log(parseInt("4", 3, ["1", "2", "3", "4", "5"])); // NaN
// console.log(parseInt("5", 4, ["1", "2", "3", "4", "5"])); // NaN

console.log(["1", "2", "3", "4", "5"].map(item => parseInt(item))); // [1, 2, 3, 4, 5]
```

# Array.prototype.push(element1[, ...[, elementN]])
* 원본 배열의 끝에 인수로 전달받은 값들을 추가하고, 추가한 후의 length 프로퍼티 값을 반환함
```javascript
const arr = [1, 2, 3];
console.log(arr.push(4, 5)); // 5
console.log(arr); // [1, 2, 3, 4, 5]
```
* 배열에 요소를 추가하는 방법으로는 arr[index]도 있음
```javascript
const arr = [1, 2, 3];
arr[3] = 4;
console.log(arr); // [1, 2, 3, 4]
arr[arr.length] = 5; // arr.push(5)와 동일하나, 이 방법이 속도가 더 빠름
console.log(arr); // [1, 2, 3, 4, 5]
```

# javascript의 배열 생성
* Array() 생성자 함수 또는 배열 리터럴 []을 사용하여 배열을 생성할 수 있음
* 배열 리터럴도 내부적으로는 Array() 생성자 함수를 사용하므로 기능의 차이는 없음
* Array()의 인자로 Number 타입을 받으면 해당 인자와 같은 크기의 빈 배열을 생성하고, Number 타입이 아니면 해당 인자를 첫 번째 요소로 하는 배열을 생성함

```javascript
const a = new Array(2); // 크기가 2인 빈 배열 생성
const b = new Array("2"); // ["2"]
const c = new Array(2.5); // Uncaught RangeError: Invalid array length (정수가 아닌 Number 타입을 인자로 받으면 RangeError 발생)
```
