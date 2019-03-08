# const

* 상수로써, 재할당 할 수 없는 변수
* 변수 자체가 변경되지 않고 할당된 내용만 변경하지 못하게 함.
* 객체인 경우 객체 자체는 여전히 변경 가능

```javascript
// es6
const PI = 3.141593
PI > 3.0

// es5
//  only in ES5 through the help of object properties
//  and only in global context and not in a block scope
Object.defineProperty(typeof global === "object" ? global : window, "PI", {
    value:        3.141593,
    enumerable:   true,
    writable:     false,
    configurable: false
})
PI > 3.0;
```

