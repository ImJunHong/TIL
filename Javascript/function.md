# Arrow function(화살표 함수)
* (params) => {function body} 형태로 사용
* 소괄호 안에 여러 개의 매개변수를 선언할 수 있고, 매개변수가 단 한 개인 경우 소괄호를 생략할 수 있음
* 함수 몸체가 하나의 문(statement)으로 구성되어 있다면 중괄호를 생략할 수 있음
* 중괄호 생략시, 함수 몸체의 문이 표현식(expression)이라면 해당 표현식이 반환됨
```javascript
const sayHello = () => console.log("Hello World"); // 매개변수 없음(소괄호 생략 불가)
sayHello(); // Hello world

const sqrt = x => Math.sqrt(x); // 매개변수 1개 일 때 소괄호 생략 가능
                                // Math.sqrt(x)는 값으로 평가될 수 있는 표현식이므로 반환됨
                                // x => { return Math.sqrt(x); };와 같음
console.log(sqrt(4)); // 2

const sum = (x, y) => x + y; // 여러 개의 매개변수를 선언할 경우 소괄호 생략 불가
console.log(sum(1, 2)); // 3

const makeEmptyObject = () => ({}); // 중괄호 생략시에 객체 리터럴을 반환할 때에는 반드시 소괄호로 감싸야 함({function body}와 구분하기 위함)
                                    // () => { return {}; };와 같음

const factorial = x => {
    let prod = 1;
    for(let i = x; i > 1; i--) prod *= i
    return prod; // 함수 몸체에 여러 줄을 사용할 때 반환값이 필요할 경우 명시적으로 return문을 작성해야 함
}
console.log(factorial(5)); // 120
```
## 일반 함수와의 차이점
* 화살표 함수는 인스턴스를 생성할 수 없음
* 중복된 매개변수 이름을 선언할 수 없음
* 화살표 함수 자체의 this, arguments, super, new.target을 갖지 않음
``` javascript
const sayHello = () => console.log("Hello World");
new sayHello(); // Uncaught TypeError: sayHello is not a constructor

const sum = (x, x) => x + x; // Uncaught SyntaxError: Duplicate parameter name not allowed in this context

const Foo = (function () {
    function Foo(num) {
        this.num = num;
    }
    Foo.prototype.method = function (arr) {
        return arr.map(item => item % this.num); // 화살표 함수 대신 일반 함수를 사용하면 this는 전역 객체를 가리킴
    }
    return Foo;
}());

const arrow = new Foo(3);
console.log(arrow.method([1, 2, 3])); // (3) [1, 2, 0]
```

# new.target
* constructor인 함수 내부에서 new 연산자로 호출된 함수에서는 함수 자신을 가리킴
* new 연산자로 호출되지 않고 일반 함수로서 호출되었다면 undefined를 가리킴
* ES6부터 지원함
```javascript
function Foo() {
    if (!new.target) {
        console.log("This function is called without new.");
        return;
    }
    console.log("This function is called with new.");
}

Foo(); // This function is called without new.
new Foo(); // This function is called with new.
```

* constructor 함수를 new 연산자로 호출하지 않았을 때에도 생성자 함수로서 호출하기
```javascript
function Foo() {
    if (!new.target) {
        return new Foo();
    }
}
```
* new.target이 지원되지 않는 환경에서의 polyfill
```javascript
// 만약 new 연산자로 호출되지 않았다면 this는 전역 객체를 가리킴
function Foo() {
    if (!(this instanceof Foo)) {
        return new Foo();
    }
}
```
