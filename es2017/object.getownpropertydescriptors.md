# Object.getOwnPropertyDescriptors

* object내 가지고 있는 descriptor의 정보를 반환
* `configuable`, `enumerable`, `writable`, `get`, `set`, `value` 값 포함

```javascript
const obj = { 
  get es7() { return 777; },
  get es8() { return 888; }
};
Object.getOwnPropertyDescriptors(obj);
// {
//   es7: {
//     configurable: true,
//     enumerable: true,
//     get: function es7(){}, //the getter function
//     set: undefined
//   },
//   es8: {
//     configurable: true,
//     enumerable: true,
//     get: function es8(){}, //the getter function
//     set: undefined
//   }
// }
```

