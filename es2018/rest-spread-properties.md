# Rest/Spread Properties

ES2015에 추가된 기능 중 하나는 Rest/Spread 연산자 입니다. 이 연산자는 배열의 복사 및 병합을 단순하게 만들어 줄 수 있습니다.

concat\(\) 또는 slice\(\) 메서드를 호출하는 대신 ...연산자를 사용할 수 있습니다.

```javascript
const arr1 = [10, 20, 30];

// make a copy of arr1
const copy = [...arr1];

console.log(copy);    // → [10, 20, 30]

const arr2 = [40, 50];

// merge arr2 with arr1
const merge = [...arr1, ...arr2];

console.log(merge);    // → [10, 20, 30, 40, 50]
```

spread 연산자는 배열이 함수에 대한 별도의 인수로 전달되어야 하는 상황에서도 유용하게 사용됩니다.

```javascript
const arr = [10, 20, 30]

// equivalent to
// console.log(Math.max(10, 20, 30));
console.log(Math.max(...arr));    // → 30
```

ES2018에서는 spread 속성을 리터럴에 추가하여 해당 구문을 확장시켜서 사용합니다. spread 속성을 사용하면,  객체 내 자체 열거가 가능하여 새 객체에 복사가 가능합니다.

```javascript
const obj1 = {
  a: 10,
  b: 20
};

const obj2 = {
  ...obj1,
  c: 30
};

console.log(obj2); 
```

이 코드에서 ... 연산자는 obj1의 속성을 검색하고 obj2에 할당하는 데 사용됩니다. ES2018 이전에는 오류가 발생했습니다. 같은 이름의 속성이 여러 개있는 경우 마지막에 오는 속성이 사용됩니다.

```javascript
const obj1 = {
  a: 10,
  b: 20
};

const obj2 = {
  ...obj1,
  a: 30
};

console.log(obj2);    // → {a: 30, b: 20}
```

spread 속성은 두개 이상의 객체를 병합하는 방법을 통해서 Object.assign\(\) 메소드의 대안으로 사용 가능합니다.

```javascript
const obj1 = {a: 10};
const obj2 = {b: 20};
const obj3 = {c: 30};

// ES2018
console.log({...obj1, ...obj2, ...obj3});    // → {a: 10, b: 20, c: 30}

// ES2015
console.log(Object.assign({}, obj1, obj2, obj3));
```

