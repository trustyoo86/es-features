# Promise

* Asynchronously \(비동기\)  실행을 위한 promise 객체 지원
* `resolve`, `reject` function을 통해  비동기 실행 절차 제어
* `then(resolve)`, `catch(reject)` 를 통해 처리

```javascript
function msgAfterTimeout (msg, who, timeout) {
    return new Promise((resolve, reject) => {
        setTimeout(() => resolve(`${msg} Hello ${who}!`), timeout)
    })
}
msgAfterTimeout("", "Foo", 100).then((msg) =>
    msgAfterTimeout(msg, "Bar", 200)
).then((msg) => {
    console.log(`done after 300ms:${msg}`)
})
```

