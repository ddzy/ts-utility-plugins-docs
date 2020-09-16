# dropRight

### 说明

从源数组的右侧开始, 舍弃指定个数的值

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/dropRight](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/dropRight)

### 用法

{% code title="dropRight.test.ts" %}
```typescript
import { dropRight } from "../../utility/array/dropRight";

describe('dropRight tests...', () => {
  test('dropRight should return an empty array when receive an empty array', () => {
    const received: number[] = [];
    const expected = [];

    const result = dropRight<number>(received);

    expect(result.length).toBe(expected.length);
  });

  test('dropRight should return the processed array correctly', () => {
    const received: number[] = [1, 2, 3, 4, 5];
    const expected = [1, 2, 3];

    const result = dropRight<number>(received, 2);

    result.forEach((v, i) => {
      expect(v).toBe(expected[i]);
    });
  });

  test('dropRight should not change the origin array', () => {
    const received: number[] = [1, 2, 3, 4, 5, 6];

    const result = dropRight(received);

    result.push(100, 200);

    expect(result.length).toBe(7);
    expect(received.length).toBe(6);
  });
});
```
{% endcode %}

