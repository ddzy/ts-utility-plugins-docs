# castArray

### 说明

将给定的值强制转成数组

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/castArray](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/castArray)

### 用法

{% code title="castArray.test.ts" %}
```typescript
import { castArray } from "../../utility/array/castArray";

describe('castArray', () => {
  test('castArray should convert the passed value to array forcibly', () => {
    interface IObjParams {
      age: number,
    };
    const obj: IObjParams = {
      age: 21,
    };

    const received = [
      0,
      undefined,
      null,
      'ddzy',
      obj,
    ];
    const expected = [
      [0],
      [undefined],
      [null],
      ['ddzy'],
      [obj],
    ];

    for (const [i, v] of received.entries()) {
      const result = castArray<typeof v>(v) as any[];

      expect(result[0]).toBe(expected[i][0]);
    }
  });

  test('castArray should return it immediatly when receive an array', () => {
    const arr: number[] = [];

    const received = [
      arr,
    ];
    const expected = [
      arr,
    ];

    for (const [i, v] of received.entries()) {
      const result = castArray<number[]>(v) as number[];

      expect(result).toBe(expected[i]);
    }
  });
});
```
{% endcode %}

