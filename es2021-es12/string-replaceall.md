# String replaceAll()

`String.prototype.replaceAll()` - 문자열의 모든 내용을 다른 문자열 값으로 바꿈

현재에는 `replace()` 메소드가 있어 문자열을 다른 문자열로 바꾸는데 사용

```javascript
const str = "Backbencher sits at the Back";
const newStr = str.replace("Back", "Front");
console.log(newStr); // "Frontbencher sits at the Back"
```

입력 패턴이 문자열인 경우 replace() method는 첫번째 항목만 바꿈 (두번째 항목은 바뀌지 않음)

`replaceAll()` 메소드의 경우 전체 문자열을 바꿀 수 있음 (정규식 이용)

```javascript
const str = "Backbencher sits at the Back";
const newStr = str.replace(/Back/g, "Front");
console.log(newStr); // "Frontbencher sits at the Front"
```

문자열인 경우에도 사용 가능

```javascript
const str = "Backbencher sits at the Back";
const newStr = str.replaceAll("Back", "Front");
console.log(newStr); // "Frontbencher sits at the Front"
```
