# Nullish Coalescing

* `null` 또는 `undefined` 값에서 발생하는 또다른 문제는 해당 타입일 경우 원하는 변수를 설정하기 위해서 기본값을 만들어야 함.

```javascript
const y = x || 500;
```

* `||`를 사용해서 x가 정의되지 않은 경우 기본값을 만들어야함.
* 그러나, 해당 부분은 0, false 또는 빈 문자열과 같은 모든 잘못된 값이 포함됨
* 이를 수정하기 위해 `Nullish Coalescing(Nullish 연산자)` 제안
* `??` 연산자 사용 - null이거나 undefined인 경우에만 기본값을 설정

```javascript
const y = x ?? 500;
```

```javascript
const x = null;
const y = x ?? 500;
console.log(y); // 500

const n = 0
const m = n ?? 9000;
console.log(m) // 0
```

* x에 null 값이 존재하기 때문에 y에 500이 할당됨.
* 두번째 x가 null이 아니거나 undefined가 아닌 경우 `||`를 사용하게 되면 9000이 출력됨.
* 해당 기능은 현재 Babel에 최신 버전 사용해야함.
