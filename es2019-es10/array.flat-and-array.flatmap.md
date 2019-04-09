# Array.flat & Array.flatMap

#### Array.flat

* 다중 배열을 평평하게 만들기 위한 기능
* 인자로는 depth가 있으며 기본값은 1

```javascript
const arr1 = [1, 2, [3, 4]];
arr1.flat();
console.log(arr1); // [1, 2, 3, 4]

const arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
console.log(arr2); // [1, 2, 3, 4, [5, 6]]

const arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
console.log(arr3); // [1, 2, 3, 4, 5, 6]

const arr4 = [1, 2, , 4, 5];
arr4.flat();
console.log(arr4); // [1, 2, 4, 5]
```

#### Array.flatMap

* map과 flat을 조합한 기능
* 다차원으로 쌓인 배열이 아닌 1차원배열로 평탄화

```javascript
/** map */
const arr1 = [1, 2, 3, 4];
const arrMap = arr1.map(v => [v, v * 2]);
console.log(arrMap); // [[1, 2], [2, 4], [3, 6], [4, 8]]

/** map + flat */
const arr2 = [1, 2, 3, 4];
const arrMapFlat = arr2.map(v => [v, v * 2]).flat();
console.log(arrMapFlat); // [1, 2, 2, 4, 3, 6, 4, 8]

/** flatMap */
const arr3 = [1, 2, 3, 4];
const arrFlatMap = arr3.flatMap(v => [v, v * 2]);
console.log(arrFlatMap); // [1, 2, 2, 4, 3, 6, 4, 8]
```

