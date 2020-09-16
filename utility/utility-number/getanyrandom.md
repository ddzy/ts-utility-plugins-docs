# getAnyRandom

### 说明

 获取指定范围内的随机`自然数`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/number/getAnyRandom](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/number/getAnyRandom)

### 用法

{% code title="getAnyRadian.test.ts" %}
```typescript
import { getAnyRandom } from "../../utility/number/getAnyRandom";


describe('getAnyRandom', () => {
  test('getAnyRandom should receive two numbers and return a float number or a interger between these two numbers ', () => {
    const origin = [
      {
        min: 0,
        max: 10,
      },
      {
        min: Number.MIN_SAFE_INTEGER,
        max: Number.MAX_SAFE_INTEGER,
      },
      {
        min: -1,
        max: 1,
      }
    ];

    for (const v of origin) {
      const { min, max } = v;

      const result = getAnyRandom(
        min,
        max,
      );

      expect(typeof result).toBe('number');
      expect(result >= min && result <= max).toBeTruthy();
    }
  });
});
```
{% endcode %}

