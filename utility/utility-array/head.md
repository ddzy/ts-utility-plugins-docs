# head

### 说明

 获取指定数组的第`一`个元素

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/head](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/head)

### 用法

{% code title="head.test.ts" %}
```typescript
import { head } from "../../utility/array/head";

describe('head tests: ', () => {
  test('head should return the first field that was in origin array', () => {
    const received: number[] = [1, 2, 3, 4, 5];
    const expected = 1;

    const result = head<number>(received);

    expect(result).toBe(expected);
  });

  test('head should return undefined when receive an empty array', () => {
    const received: any[] = [];
    const expected = undefined;

    const result = head<any>(received);

    expect(result).toBe(expected);
  });
});
```
{% endcode %}

