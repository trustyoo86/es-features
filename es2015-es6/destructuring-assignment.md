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

