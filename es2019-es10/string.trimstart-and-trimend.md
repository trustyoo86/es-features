# String.trimStart & trimEnd

* `trimStart`는 문자열의 시작지점의 개행을 삭제함
* `trimEnd`는 문자열의 종료지점의 개행을 삭제함

```javascript
const greeting = ` Hello Javascript! `;
greeting.length;
> 19
greeting = greeting.trimStart();
> 'Hello Javascript! '
greeting.length;
> 18
greeting = 'Hello World!   ';
greeting.length;
> 15
greeting = greeting.trimEnd();
> 'Hello World!'
greeting.length;
> 12
```

