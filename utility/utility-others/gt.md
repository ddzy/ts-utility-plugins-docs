# gt

### 说明

 检查`x`是否大于`y`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/gt](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/gt)

### 用法

{% code title="gt.test.ts" %}
```typescript
import { gt } from "../../utility/others/gt";

describe('gt tests: ', () => {

  test('gt should return `true` when the param 1 that large than param2', () => {
    const received = [10, 5];
    const expected = true;

    const result = gt(received[0], received[1]);

    expect(result).toBe(expected);
  });

  test('gt should return `false` when the param 1 that equal with param2', () => {
    const received = [10, 10];
    const expected = false;

    const result = gt(received[0], received[1]);

    expect(result).toBe(expected);
  });

  test('gt should return `false` when the param 1 that small than param2', () => {
    const received = [10, 20];
    const expected = false;

    const result = gt(received[0], received[1]);

    expect(result).toBe(expected);
  });

});
```
{% endcode %}

