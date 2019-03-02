# 2\) for...await...of

* 일반적으로 iterator는 next\(\) 함수를 이용하여 generator 객체를 반환
* next\(\) 실행시 {value, done} 객체를 포함하여 반환
* asyncIterator는 promise 객체를 이용 {value, done} 객체를 반환함.
* iterator객체를 쉽게 이용할 수 있는 방법은 `for...of` 를 이용하는 방법임.
* 그러나 asyncIterator는 `for..of` 문법을 이용하여 사용할 수 없음.

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

(async function () {
  for await (const x of collection) {
    console.log(x);
  }
})();

// logs:
// → 10
// → 20
// → 30
```

* for...await...of 문은 암시적으로 asyncIterator를 호출하여 비동기 promise를 반환함.
* 반복문이 실행될때마다 next\(\)를 호출하여 value를 가진 promise를 받음
* promise가 resolve되면 x변수에는 해당 value값이 읽혀짐.
* loop는 done property가 true가 될때까지 반복됨.
* **for...await...of문은 asyncIterator 또는 비동기 함수에서만 동작 가능함.**
* 해당 규칙 위반시 syntax error 발생



