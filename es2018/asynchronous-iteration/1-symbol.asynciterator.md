# 1\) Symbol.asyncIterator

* 비동기 iterator
* 기존 Symbol.iterator의 경우 비동기 데이터를 출력하는데 적절하지 않음.
* 일반 객체를 value, done 형태로 반환하는 대신 value, done을 충족하는 promise를 반환함.

```javascript
onst collection = {
  a: 10,
  b: 20,
  c: 30,
  [Symbol.asyncIterator]() {
    const values = Object.keys(this);
    let i = 0;
    return {
      next: () => {
        return Promise.resolve({
          value: this[values[i++]], 
          done: i > values.length
        });
      }
    };
  }
};

const iterator = collection[Symbol.asyncIterator]();
  
console.log(iterator.next().then(result => {
  console.log(result);    // → {value: 10, done: false}
}));

console.log(iterator.next().then(result => {
  console.log(result);    // → {value: 20, done: false} 
}));

console.log(iterator.next().then(result => {
  console.log(result);    // → {value: 30, done: false} 
}));

console.log(iterator.next().then(result => {
  console.log(result);    // → {value: undefined, done: true} 
}));
```

* `iterator.next().then()` 을통해 promise를 받아서 결과값을 처리해야함.
* result내의 `done` 상태 파악 필요함.

```javascript
const collection = {
  a: 10,
  b: 20,
  c: 30,
  [Symbol.asyncIterator]: async function * () {
    for (let key in this) {
      yield this[key];
    }
  }
};

const iterator = collection[Symbol.asyncIterator]();
  
console.log(iterator.next().then(result => {
  console.log(result);    // → {value: 10, done: false}
}));

console.log(iterator.next().then(result => {
  console.log(result);    // → {value: 20, done: false} 
}));

console.log(iterator.next().then(result => {
  console.log(result);    // → {value: 30, done: false} 
}));

console.log(iterator.next().then(result => {
  console.log(result);    // → {value: undefined, done: true} 
}));
```



