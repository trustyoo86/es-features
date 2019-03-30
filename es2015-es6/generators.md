# Generators

* function 내의 `*` 와 `yield`를 이용 할수  있음.
* `yield` 구문은 return과 비슷하나, 해당 흐름을 제어하며 여러번 호출할 수 있는 점이 특징임.
* generator function의 Symbole iterator 구문으로, `next()` function을 통해서 yield에 정의된 구문을 순차적으로 실행 가능.

```javascript
// generator func
function* quips(name) {
  yield "hello " + name + "!";
  yield "i hope you are enjoying the blog posts";
  if (name.startsWith("X")) {
    yield "it's cool how your name starts with X, " + name;
  }
  yield "see you later!";
}
```

```javascript
var iter = quips("jorendorff");
  [object Generator]
iter.next()
  { value: "hello jorendorff!", done: false }
iter.next()
  { value: "i hope you are enjoying the blog posts", done: false }
iter.next()
  { value: "see you later!", done: false }
iter.next()
  { value: undefined, done: true }
```

