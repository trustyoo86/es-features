# 2\) Rest Parameter

* 가변의 인수를 집합으로 만들어 사용 가능.
* Rest Parameter는 function내의 인수 집합을 풀때 사용

```javascript
// es6
function f (x, y, ...a) {
    return (x + y) * a.length
}
f(1, 2, "hello", true, 7) === 9

// es5
function f (x, y) {
    var a = Array.prototype.slice.call(arguments, 2);
    return (x + y) * a.length;
};
f(1, 2, "hello", true, 7) === 9;
```

