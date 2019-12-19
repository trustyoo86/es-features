# Symbol objects description property

Symbol 타입으로 객체 추가시 디버깅 목적을 위해 description property 추가가 가능합니다.
이 경우 Symbol 객체에 읽기 전용 description property를 추가할 수 있으며, Symbol에 설명이 포함된 문자열을 반환합니다.

```javascript
let sym = Symbol('foo');
console.log(sym.description);    // => foo

sym = Symbol();
console.log(sym.description);    // => undefined

// create a global symbol
sym = Symbol.for('bar');
console.log(sym.description);    // => bar
```