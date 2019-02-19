# 2\) Object merge

두개 Object를 병합하여 assign method 대신 사

* 새로 할당하는 object내 같은 property가 있는경우 merge

```javascript
const obj1 = {
  a: 10,
  b: 20
};

const obj2 = {
  ...obj1,
  a: 30
};

console.log(obj2);    // → {a: 30, b: 20}
```

```javascript
const obj1 = {a: 10};
const obj2 = {b: 20};
const obj3 = {c: 30};

// ES2018
console.log({...obj1, ...obj2, ...obj3});    // → {a: 10, b: 20, c: 30}

// ES2015
console.log(Object.assign({}, obj1, obj2, obj3));
```

