# inRange

### 说明

 检查指定值是否在 `start` 与 `end` 之间, 但是不包括 `end`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/number/inRange](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/number/inRange)

### 用法

{% code title="inRange.test.ts" %}
```typescript
import { inRange } from "../../utility/number/inRange";


describe('inRange tests...', () => {
  test('method inRange should compute the correct result', () => {
    const received = [
      {
        value: 0,
        start: 100,
        end: 200,
      },
      {
        value: 45,
        start: -11,
        end: 98,
      },
      {
        value: 34,
        start: 34,
        end: 34,
      },
      {
        value: 0,
        start: -344,
        end: 0,
      },
    ];
    const expected = [false, true, false, false];

    received.forEach((v, i) => {
      const result = inRange(v.value, v.start, v.end);

      expect(result).toBe(expected[i]);
    });
  });
});
```
{% endcode %}

