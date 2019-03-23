# Destructuring Assignment

* 디스트럭쳐링 \(Destructuring\) 이란 Object 혹은 Array를 분해하는 의미를 가지고 있
* 배열을 분해하여 할당 가능함.

```javascript
// es6
var list = [ 1, 2, 3 ]
var [ a, , b ] = list
[ b, a ] = [ a, b ]

// es5
var list = [ 1, 2, 3 ];
var a = list[0], b = list[2];
var tmp = a; a = b; b = tmp;
```

* Object를 분해하여 할당

```javascript
// es6
var { op, lhs, rhs } = getASTNode()

// es5
var tmp = getASTNode();
var op  = tmp.op;
var lhs = tmp.lhs;
var rhs = tmp.rhs;
```

* function내에서 destructuring을 이용한 참조변수 활용 가능

```javascript
function f ([ name, val ]) {
    console.log(name, val) // bar 42
}
// 변수로 할당 가능
function g ({ name: n, val: v }) {
    // foo 7
    console.log(n, v)
}
function h ({ name, val }) {
    console.log(name, val)
}
f([ "bar", 42 ])
g({ name: "foo", val:  7 })
h({ name: "bar", val: 42 })
```

* array내 변수가 없는 경우 할당으로 가능

```javascript
var list = [ 7, 42 ]
var [ a = 1, b = 2, c = 3, d ] = list
a === 7
b === 42
c === 3
d === undefined
```

