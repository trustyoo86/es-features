# Template Literal Revision

```javascript
function fn(string, substitute) {
  if(substitute === 'ES6') {
    substitute = 'ES2015'
  }
  return substitute + string[1];
}

const version = 'ES6';
const result = fn`${version} was a major update`;

console.log(result);    // → ES2015 was a major update
```

* 정규표현식인 태그 표현식 호출되어 템플릿 리터럴 전달
* 문자열의 동적인 부분 수정하고 반환
* ES2018 이전에 태그가 지정된 템플릿 리터럴에 이스케이프 관련된 제약이 존재
* 이스케이프로 인한 Syntax error 발생
* ES2018에서는 syntax error 발생 대신 undefined 반환

```javascript
function fn(string, substitute) {
  console.log(substitute);    // → escape sequences:
  console.log(string[1]);     // → undefined
}

const str = 'escape sequences:';
const result = fn`${str} \ubuntu C:\xxx\uuu`;
```

