# 1\) s\(dotAll\) flag

* dot \(.\)
  * 줄바꿈 \(\n\) 또는 캐리지리턴 \(\r\)과 같은 줄 바꿈 문자를 제외한 모든 문자와 일치하는 일반 표현식 패턴의 정규식 특수문자
  * 이전에는 줄 바꿈을 포함 모든 문자를 일치시키는 해결 방법은 `\\d\\D` 로 표현해야 했음

```javascript
console.log(/one[\d\D]two/.test('one\ntwo'));    // → true
```

* s flag를 사용하여 정규식 단위로 테스트 가능

```javascript
console.log(/one.two/.test('one\ntwo'));     // → false
console.log(/one.two/s.test('one\ntwo'));    // → true
```

* 이전버전과 호환 가능하기 때문에 기존 정규식 패턴에 영향받지 않음.

