# Dynamic import

* file import를 동적으로 수행 가능
* promise 형태로 return

```js
const numbs = [1,2,3];

if (numbs.length) {
  const math = '../math';
  import(math)
    .then(module => {
      module.max(...numbs);
    });
}
```

* `async/await` 문 사용 가능

```js
const math = '../math.js';
const module = await import(math);
module.max(...numbs);
```

## Browser support
* Chrome: 63
* Edge: 지원안함 (chromium 버전 x)
* Firefox: 67
* IE: 지원안함
* Opera: 50
* Safari: 11.1
