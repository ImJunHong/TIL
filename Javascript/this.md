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
    console.log(this); // global
}
foo();
```
* 함수가 중첩되어도 일반 함수로서 호출되면 항상 전역 객체를 가리킴
```javascript
function foo() {
    console.log(this); // global
    function foo2() {
        console.log(this); // global
        function foo3() {
            console.log(this); // global
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
method(); // undefined undefined
```
