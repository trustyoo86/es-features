# 1\) spread 속성을 이용한 객체복사

spread를 이용하여 객체 복사 가능

* obj1을 obj2에 spread형태로 할당

```javascript
const obj1 = {
  a: 10,
  b: 20
};

const obj2 = {
  ...obj1,
  c: 30
};

console.log(obj2); 
```



