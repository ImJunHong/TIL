# ==와 ===의 차이점
* ==는 동등 연산자(equality operator)이고, ===는 일치 연산자(strict equality operator / identity operator)임
* ==는 피연산자의 타입이 다르면 타입을 변환하여 값을 비교하고, ===는 타입과 값이 모두 동일한지를 비교함
```javascript
0 == "" // true
0 == "0" // true
0 == false // true
1 == true // true
0 == [] // true
"0" == [] // false
0 == undefined // false
0 == null // false
null == undefined // true
null == false // false
false == undefined // false
NaN == NaN // false (NaN은 원래 어떤 것과도 일치하지 않음)

// == 연산자 대신 === 연산자 사용시 위의 모든 식에 대해 false 반환
```
