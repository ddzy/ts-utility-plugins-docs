# isFunction

### 说明

 检查是否`函数`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/isFunction](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/isFunction)

### 用法

{% code title="isFunction.test.ts" %}
```typescript
import { isFunction } from "../../utility/function/isFunction";

describe('isFunction', () => {
  test('isFunction should return `true` when received a function object', () => {
    const origin = [
      function () { },
      Symbol,
    ];

    for (const v of origin) {
      expect(isFunction(v)).toBeTruthy();
    }
  });
});
```
{% endcode %}

