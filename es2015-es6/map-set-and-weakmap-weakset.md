# Map/Set & WeakMap/WeakSet

* new Set\(\) 을 이용해서 object 형태의 Map 객체 생성 가능
* `add` `has` function 사용 가능
* `for...of` 활용 가능

```javascript
let s = new Set()
s.add("hello").add("goodbye").add("hello")
s.size === 2
s.has("hello") === true
for (let key of s.values()) // insertion order
    console.log(key)
```

