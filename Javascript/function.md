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
// 만약 new 연산자로 호출되지 않았다면 this는 전역 객체를 
function Foo() {
    if (!(this instanceof Foo)) {
        return new Foo();
    }
}
```
