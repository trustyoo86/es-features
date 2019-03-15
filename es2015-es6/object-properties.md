# Object properties

* shorthand \(축약\) 형태로 object property 표현 가능

```javascript
// es6
var x = 0, y = 0
obj = { x, y }

// es5
var x = 0, y = 0;
obj = { x: x, y: y };
```

* computed name property \(프로그래밍형태의 property 바인딩\) 가능

```javascript
// es6
let obj = {
    foo: "bar",
    [ "baz" + quux() ]: 42
}

// es5
var obj = {
    foo: "bar"
};
obj[ "baz" + quux() ] = 42;
```

* method 표기법 사용 가능
* generator function도 가

```javascript
// es6
obj = {
    foo (a, b) {
        …
    },
    bar (x, y) {
        …
    },
    *quux (x, y) {
        …
    }
}

// es5
obj = {
    foo: function (a, b) {
        …
    },
    bar: function (x, y) {
        …
    },
    //  quux: no equivalent in ES5
    …
};
```

