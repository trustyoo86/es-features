# 1\) Defulat Paramter values

* function 내에서 default value를 정할 수 있음

```javascript
// es6
function f (x, y = 7, z = 42) {
    return x + y + z
}
f(1) === 50

// es5
function f (x, y, z) {
    if (y === undefined)
        y = 7;
    if (z === undefined)
        z = 42;
    return x + y + z;
}
f(1) === 50;
```

