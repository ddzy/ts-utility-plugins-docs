# isDOM

### 说明

 检查是否`DOM`元素

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/isDOM](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/isDOM)

### 用法

{% code title="isDOM.test.ts" %}
```typescript
import { isDOM } from "../../utility/dom/isDOM";

describe('isDOM', () => {
  test('isDOM should return `false` if  received a non DOM object', () => {
    const origin = [
      0, Number.MAX_SAFE_INTEGER, Number.MIN_VALUE,
      '', 'ddzy',
      {},
      true, false,
      function () { },
      [],
    ];

    for (const v of origin) {
      expect(isDOM(v)).toBeFalsy();
    }
  });

  test('isDOM should return `true` if  received a DOM object', () => {
    const origin = [
      document.createElement('div'),
      document.body
    ];

    for (const v of origin) {
      expect(isDOM(v)).toBeTruthy();
    }
  });
});
```
{% endcode %}

