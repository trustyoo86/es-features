# 1\) Map data-structure

* Symbol type의 data set 가능

```javascript
let m = new Map()
let s = Symbol()
m.set("hello", 42)
m.set(s, 34)
m.get(s) === 34
m.size === 2
for (let [ key, val ] of m.entries()) {
    console.log(key + " = " + val);
}
```

