# isNull

### 说明

 判断是否为严格的`null`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/isNull](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/isNull)

### 用法

{% code title="isNull.test.ts" %}
```typescript
import { isNull } from "util";


describe('isNull', () => {
  test('isNull should return `false` if received a non null value', () => {
    const received = [
      0,
      '',
      undefined,
      {},
      [],
      function () { },
    ];

    for (const v of received) {
      expect(isNull(v)).toBeFalsy();
    }
  });

  test('isNull should return `true` if received a null value', () => {
    const received = [
      null,
    ];

    for (const v of received) {
      expect(isNull(v)).toBeTruthy();
    }
  });
});
```
{% endcode %}

