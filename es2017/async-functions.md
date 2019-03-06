# Async functions

* `AsyncFunction` object를 반환하는 function 선언
* 내부적으로 generator처럼 실행되나, 실제로 generator function을 해석하지 않음

```javascript
function fetchTextByPromise() {
  return new Promise(resolve => { 
    setTimeout(() => { 
      resolve("es8");
    }, 2000);
  });
}
async function sayHello() { 
  const externalFetchedText = await fetchTextByPromise();
  console.log(`Hello, ${externalFetchedText}`); // Hello, es8
}
sayHello();
```

* `sayHello` 로그 출력 후 2초 후 `Hello, es8` 로그가 출력됨

```javascript
console.log(1);
sayHello();
console.log(2);
```

```bash
1 // immediately
2 // immediately
Hello, es8 // after about 2 seconds
```

* `async function`은 언제나 `promise 객체`를 반환하며, `await` 키워드는 언제나 `async function` 내에서만 사용 가능함.

