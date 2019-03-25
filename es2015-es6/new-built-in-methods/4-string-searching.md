# 4\) string searching

* `startsWith(value, index)` - index부터 value를 찾음
* `endsWith(value, index)` - index부터 역순으로  value를 찾음
* `includes(value, index)` - index부터 value를 찾음. value만으로 검색 가능

```javascript
"hello".startsWith("ello", 1) // true
"hello".endsWith("hell", 4)   // true
"hello".includes("ell")       // true
"hello".includes("ell", 1)    // true
"hello".includes("ell", 2)    // false
```

