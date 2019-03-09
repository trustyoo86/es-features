# Arrow Functions

* `() =>` 을 통해서 함수 표현 가능
* 외부의 scope를 가짐
* 함수표현식

```javascript
// es6
odds  = evens.map(v => v + 1)
pairs = evens.map(v => ({ even: v, odd: v + 1 }))
nums  = evens.map((v, i) => v + i)
nums.forEach(v => {
   if (v % 5 === 0)
       fives.push(v)
})

// es5
odds  = evens.map(function (v) { return v + 1; });
pairs = evens.map(function (v) { return { even: v, odd: v + 1 }; });
nums  = evens.map(function (v, i) { return v + i; });
nums.forEach(function (v) {
   if (v % 5 === 0)
       fives.push(v);
});
```

* this scope 정의

```javascript
// es6
this.nums.forEach((v) => {
    if (v % 5 === 0)
        this.fives.push(v)
})

// es5 첫번째 표현
var self = this;
this.nums.forEach(function (v) {
    if (v % 5 === 0)
        self.fives.push(v);
});

// es5 두번째 표현
this.nums.forEach(function (v) {
    if (v % 5 === 0)
        this.fives.push(v);
}, this);

// es5 세번째 표현 (only ECMAScript 5.1)
this.nums.forEach(function (v) {
    if (v % 5 === 0)
        this.fives.push(v);
}.bind(this));
```

