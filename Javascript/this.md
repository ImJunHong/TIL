# 전역에서의 this
* 전역에서의 this는 전역 객체(브라우저의 window, Node.js의 global)를 가리킴
```javascript
// 브라우저에서 실행
console.log(this === window); // true

// Node.js에서 실행
console.log(this === global); // true
```

# 함수 내에서의 this
* 함수 호출 방식에 따라 바인딩이 동적으로 결정됨

## 일반적인 함수 호출
* 전역 객체를 가리킴
```javascript
function foo() {
    console.log(this); // window(global)
}
foo();
```
* 함수가 중첩되어도 일반 함수로서 호출되면 항상 전역 객체를 가리킴
```javascript
function foo() {
    console.log(this); // window(global)
    function foo2() {
        console.log(this); // window(global)
        function foo3() {
            console.log(this); // window(global)
        }
        foo3();
    }
    foo2();
}
foo();
```
* strict mode에서는 undefined가 바인딩됨
```javascript
function foo() {
    'use strict'
    console.log(this); // undefined
    function foo2() {
        console.log(this); // undefined
        function foo3() {
            console.log(this); // undefined
        }
        foo3();
    }
    foo2();
}
foo();
```

## 생성자 함수 호출
* 생성자 함수가 생성할 인스턴스를 가리킴
```javascript
function foo(name) {
    this.name = name;
}
const obj = new foo("Junhong");
console.log(obj.name); // Junhong
```
* new 연산자를 사용하지 않고 일반 함수로서 호출하면 전역 객체를 가리킴
```javascript
function foo(name) {
    this.name = name;
}
const obj = new foo("Junhong");
// console.log(obj.name);
// Uncaught TypeError: Cannot read property 'name' of undefined
console.log(global.name); // Junhong
```

## 메서드 호출
* 메서드 내부의 this는 해당 메서드를 호출한 객체를 가리킴
```javascript
const obj = {
    name: "Junhong",
    surname: "Lim",
    printFullName() {
        console.log(this.name + " " + this.surname);
    }
}
obj.printFullName(); // Junhong Lim
```
* printFullName을 메서드가 아닌 일반 함수로서 호출하면 전역 객체를 가리킴
```javascript
const obj = {
    name: "Junhong",
    surname: "Lim",
    printFullName() {
        console.log(this.name + " " + this.surname);
    }
}
const method = obj.printFullName
method(); // undefined(undefined undefined)
          // window.name은 ""이고, global.name은 undefined임
```

## Functions.prototype.apply/call/bind 메서드에 의한 호출
* 해당 메서드에 첫 번째 인수로 전달한 객체를 가리킴
```javascript
function foo() {
    return this;
}
const this1 = {a: 1, b: 2, c: 3};
const this2 = {a: 4, b: 5, c: 6};
const this3 = {a: 7, b: 8, c: 9};

console.log(foo.apply(this1)); // {a: 1, b: 2, c: 3}
console.log(foo.call(this2)); // {a: 4, b: 5, c: 6}
console.log(foo.bind(this3)()); // {a: 7, b: 8, c: 9}
```
