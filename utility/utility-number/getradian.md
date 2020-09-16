# getRadian

### 说明

 `角度`转`弧度`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/number/getRadian](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/number/getRadian)

### 用法

{% code title="getRadian.test.ts" %}
```typescript
import { getRadian } from "../../utility/number/getRadian";

describe('getRadian', () => {
  test('getRadian should receive an angle and convert it to radian', () => {
    const origin = [
      0,
      78,
      90,
      180,
      360
    ];
    const expected = [
      0,
      1.361356816555577,
      1.5707963267948966,
      3.141592653589793,
      6.283185307179586,
    ];
    const result: number[] = [];

    for (const v of origin) {
      result.push(getRadian(v));
    }

    for (const [i, v] of result.entries()) {
      expect(v === expected[i]).toBeTruthy();
    }
  });
});
```
{% endcode %}

