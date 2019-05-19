# 2\) Weak-Link data structure

* Memory-leak 발생 없는 data-structure 구현 가능

```javascript
let isMarked     = new WeakSet()
let attachedData = new WeakMap()

export class Node {
    constructor (id)   { this.id = id                  }
    mark        ()     { isMarked.add(this)            }
    unmark      ()     { isMarked.delete(this)         }
    marked      ()     { return isMarked.has(this)     }
    set data    (data) { attachedData.set(this, data)  }
    get data    ()     { return attachedData.get(this) }
}

let foo = new Node("foo");

JSON.stringify(foo) === '{"id":"foo"}';
foo.mark();
foo.data = "bar";
foo.data === "bar";
JSON.stringify(foo) === '{"id":"foo"}';

isMarked.has(foo)     === true;
attachedData.has(foo) === true;
foo = null;  /* foo에 대한 reference만 제거 */
attachedData.has(foo) === false;
isMarked.has(foo)     === false;
```

