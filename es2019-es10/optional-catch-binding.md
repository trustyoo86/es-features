# Optional Catch Binding

* ES10에서는 `try..catch` 문에서의 catch내 인자를 optional하게 바인딩 가능

```javascript
// Before
try {
   ...
} catch(error) {
   ...
}
// After
try {
   ...
} catch {
   ...
}
```

