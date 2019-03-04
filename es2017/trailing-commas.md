# Trailing commas

* function내 paramter에 뒤에 trailing comma 추가 가
* 이전 버전에서는 `syntax error` 반환

```javascript
function es8(var1, var2, var3,) {
  // ...
}
```

* function 호출시에도 삽입 가

```javascript
es8(10, 20, 30,);
```

