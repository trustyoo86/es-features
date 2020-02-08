# Private Fields in Classes

* Class내 `private` 변수 가능
* `#` 기호를 사용하여 private 변수임을 선언
* 외부 함수에 노출하고 싶지 않은 비공개 변수를 숨기기 위해서 클로저를 사용할 필요 없음

```javascript
class Counter {
  #x = 0;
  increment() {
    this.#x++;
  }
  decrement() {
    this.#x--;
  }
  getNum(){
    return this.#x;
  }
}
const c = new Counter();
c.increment(); 
c.increment(); 
c.decrement(); 
console.log(c.getNum());
```

마지막 `getNum`의 경우는 `#x` 변수의 값을 가져와야 함.
직접 접근하여 확인하는 경우 

```javascript
console.log(c.#x);
```

`Uncaught SyntaxError: Private field '#x'` 에러 발생
최신 버전 chrome 및 `Node.js v12`에 작성
