# 3\) reject try / catch

* `next()` 메서드의 경우 reject promise 반환시 처리 가능
* try / catch 문을 통해 `for..await` 반복자 error catch

```javascript
const collection = {
  [Symbol.asyncIterator]() {
    return {
      next: () => {
        return Promise.reject(new Error('Something went wrong.'))
      }
    };
  }
};

(async function() {
  try {
    for await (const value of collection) {}
  } catch (error) {
    console.log('Caught: ' + error.message);
  }
})();

// logs:
// → Caught: Something went wrong.
```

