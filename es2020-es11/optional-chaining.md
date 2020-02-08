# Optional Chaining Operator

* 객체에 deep하게 중첩된 속성에 엑세스 하려면 boolean을 이용하여 각 속성이 정의되어 있는지 확인해야함

```javascript
const obj = {
  prop1: {
    prop2: {
      prop3: {
        prop4: {
          prop5: 5
        }
      }
    }
  }
}
obj.prop1 &&
  obj.prop1.prop2 &&
  obj.prop1.prop2 &&
  obj.prop1.prop2.prop3 &&
  obj.prop1.prop2.prop3.prop4 &&
  console.log(obj.prop1.prop2.prop3.prop4.prop5);
```

* 원하는 속성이 있을때까지 각 속성에 정의되어 있는지 확인해야 함.
* 정의되지 않은 개체내에 중첩된 개체가 있거나, 모든 내용에 null이 있는 경우 실행되지 않음
* 충돌되지 않도록 모든 수준 확인 필요

* `Optional chaining`을 사용하기 위해서는 `?` 을 사용해야 함.
* null이거나 정의되지 않은 속성이라면 정의되지 않은 값만 반환

```javascript
const obj = {
  prop1: {
    prop2: {
      prop3: {
        prop4: {
          prop5: 5
        }
      }
    }
  }
}
console.log(obj?.prop1?.prop2?.prop3?.prop4?.prop5);
```

* undefined 혹은 null인 경우 `undefined` 상태로 복원됨
