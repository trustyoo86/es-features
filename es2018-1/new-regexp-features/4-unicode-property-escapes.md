# 4\) Unicode property escapes

* 정규표현식에서 전체 유니코드를 지원하는 이스케이프 시퀀스 제공 \(unicode escape\)
* ㉛의 경우 숫자로 간주되나 정규식에서는 ASCII \[0-9\] 문자만 지원하므로 \d 정규식 지원 안됨
* Unicode property escape의 경우는 해당 경우도 지원

```javascript
const str = '㉛';

console.log(/\d/u.test(str));    // → false
console.log(/\p{Number}/u.test(str));     // → true
```

* 알파벳 속성도 지원 가능

```javascript
const str = 'ض';

console.log(/\p{Alphabetic}/u.test(str));     // → true

// the \w shorthand cannot match ض
console.log(/\w/u.test(str));    // → false
```

* 정규식 부정문의 형태로 \p{...} 부정문인 \P{...} 사용 가능

```javascript
console.log(/\P{Number}/u.test('㉛'));    // → false
console.log(/\P{Number}/u.test('ض'));    // → true

console.log(/\P{Alphabetic}/u.test('㉛'));    // → true
console.log(/\P{Alphabetic}/u.test('ض'));    // → false
```

