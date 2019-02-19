---
description: spread property를 이용한 객체 복사의 특징을 설명합니다.
---

# 3\) spread property 객체 복사 특성

* spread 속성이 Object.assign\(\)과 동일한 결과를 생성하지는 않음

```javascript
Object.defineProperty(Object.prototype, 'a', {
  set(value) {
    console.log('set called!');
  }
});

const obj = {a: 10};

console.log({...obj});    
// → {a: 10}

console.log(Object.assign({}, obj));    
// → set called!
// → {}
```

* 위의 코드에서 Object.assign\(\) 메소드는 상속된 set 속성을 실행함.
* spread property를 이용한 속성은 set function을 무시함
* spread property는 열거 가능한 속성만 복사함.

```javascript
const car = {
  color: 'blue'
};

Object.defineProperty(car, 'type', {
  value: 'coupe',
  enumerable: false
});

console.log({...car});    // → {color: "blue"}
```

* enumerable attribute의 경우 false로 설정되어 type property의 경우 복사되지 않음
* 상속된 속성의 경우 열거 가능한 속성이 되어도 무시

```javascript
const car = {
  color: 'blue'
};

const car2 = Object.create(car, {
  type: {
    value: 'coupe',
    enumerable: true,
  }
});

console.log(car2.color);                      // → blue
console.log(car2.hasOwnProperty('color'));    // → false

console.log(car2.type);                       // → coupe
console.log(car2.hasOwnProperty('type'));     // → true

console.log({...car2});                       // → {type: "coupe"}
```

* car2는 자동차의 color attribute를 상속함.
* spread property는 객체의 자체 property만 복사하므로 반환되는 값에 색상이 포함되지 않

