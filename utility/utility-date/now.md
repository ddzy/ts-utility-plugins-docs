# now

### 说明

 获取`1970`至今的毫秒数

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/date/now](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/date/now)

### 用法

{% code title="now.test.ts" %}
```typescript
import { now } from "../../utility/date/now";

describe('now', () => {
  test('now should return a timestamp like `Date.now()` and `new Date().getTime()`', () => {
    const expected = {
      type: 'number',
    };

    const result = now();

    expect(typeof result).toBe(expected.type);
  })
})
```
{% endcode %}

