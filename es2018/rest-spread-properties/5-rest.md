---
description: rest 할당에 관련된 feature 입니다.
---

# 5\) rest 할당

```javascript
const arr = [10, 20, 30];
const [x, ...rest] = arr;

console.log(x);       // → 10
console.log(rest);    // → [20, 30]
```

* arr의 첫번째 항목은 x에 할당됨
* 나머지 요소는 rest 변수에 할당

```javascript
const obj = {
  a: 10,
  b: 20,
  c: 30
};

const {a, ...rest} = obj;

console.log(a);       // → 10
console.log(rest);    // → {b: 20, c: 30}
```

* 디스트럭쳐링 \(destructuring\) 할당에서 rest 열거가 가능한 property를 새 객체로 복사함.
* 나머지 property의 경우는 항상 객체의 끝에 할당되어야 함. \(처음에 할당하는 경우 에러\)

```javascript
const obj = {
  a: 10,
  b: 20,
  c: 30
};

const {...rest, a} = obj;    // → SyntaxError: Rest element must be last element
```

* 객체에 여러개의 rest 구문을 사용하는 경우 에러 발생

```javascript
const obj = {
  a: 10,
  b: {
    x: 20,
    y: 30,
    z: 40
  }
};

const {b: {x, ...rest1}, ...rest2} = obj;    // no error

const {...rest, ...rest2} = obj;    // → SyntaxError: Rest element must be last element
```

