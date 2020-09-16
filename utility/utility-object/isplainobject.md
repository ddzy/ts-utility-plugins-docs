# isPlainObject

### 说明

  判断是否普通的`键值对`对象

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/isPlainObject](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/isPlainObject)

### 用法

{% code title="isPlainObject.test.ts" %}
```typescript
import { isPlainObject } from "../../utility/object/isPlainObject";

describe('isPlainObject', () => {
  test('isPlainObject should return `true` if received a plain object', () => {
    const received = [
      { name: 'duan', age: 20 },
      {},
    ];

    for (const v of received) {
      expect(isPlainObject(v)).toBeTruthy();
    }
  });

  test('isPlainObject should return `false` if received a non plain object', () => {
    document.body.innerHTML += `
      <p></p>
      <p></p>
    `;

    const received = [
      document.querySelectorAll('p'),
      [1, 2, 3],
      null,
      undefined,
      0,
      '',
      false,
      true
    ];

    for (const v of received) {
      expect(isPlainObject(v)).toBeFalsy();
    }
  });
})

```
{% endcode %}

