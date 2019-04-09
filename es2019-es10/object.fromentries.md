# Object.fromEntries

* Object.entries 반대 기능
* 2차원 배열을 객체로 반환

```javascript
/** Map => Object */
const map = new Map([['foo', 'a'], ['bar', 'b']]);
const obj = Object.fromEntries(map);
console.log(obj); // { foo: 'a', bar: 'b' }

/** Array => Object */
const arr = [['foo', 'a'], ['bar', 'b']];
const obj = Object.fromEntries(arr);
console.log(obj); // { foo: 'a', bar: 'b' }
```

