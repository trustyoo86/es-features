# Array.prototype.includes\(\)

* Array method의 `indexOf()` 와 비슷함.
* Array내 요소가 포함된 경우 `true`, 포함되지 않은 경우 `false`를 반환함.
* es2016 이전

```javascript
let numbers = [1, 2, 3, 4];
if(numbers.indexOf(2) !== -1) {
  console.log('Array contains value');
}
```

* es2016 이후

```javascript
if(numbers.includes(2)) {
  console.log('Array contains value');
}
```

* NaN \(Not a Number\) 핸들링에 includes method가 indexOf 메서드보다 효율적
* `includes()` method는 NaN type 캐치하여 반환

```javascript
let numbers = [1, 2, 3, 4, NaN];
console.log(numbers.indexOf(NaN)); //Prints -1
console.log(numbers.includes(NaN)); //Prints true
```

