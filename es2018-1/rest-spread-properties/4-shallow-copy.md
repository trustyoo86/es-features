---
description: spread property를 이용한 객체 복사는 얕은 복사 (shallow copy)만 가능합니다.
---

# 4\) shallow copy

* spread property는 객체의 얕은 복사\(shallow copy\)만 가능함.

```javascript
const obj = {x: {y: 10}};
const copy1 = {...obj};    
const copy2 = {...obj}; 

console.log(copy1.x === copy2.x);    // → true
```

* copy1의 x property는 copy2의 x가 참조하는 메모리의 동일한 객체를 참조하므로 true 반환 \(strict equality operator - 완전항등연산자\)



