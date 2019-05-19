# Iterators

* 반복자 \(iterator\) 프로토콜 지원
* 반복시 {value, done} 객체 반
* `for...of` 메서드를 통해 of 앞의 ...에 변수를 강제로 반환시킴

```javascript
let fibonacci = {
    [Symbol.iterator]() {
        let pre = 0, cur = 1
        return {
           next () {
               [ pre, cur ] = [ cur, pre + cur ]
               return { done: false, value: cur }
           }
        }
    }
}

for (let n of fibonacci) {
    if (n > 1000) {
        break;
    }
    console.log(n);
}
```

