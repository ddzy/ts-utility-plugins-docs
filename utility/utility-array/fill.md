# fill

### 说明

 使用 `value` 值来填充（替换） `array`. 从 `start` 位置开始, 到 `end` 位置结束\(但不包含 `end` 位置\).

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/fill](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/fill)

### 用法

{% code title="fill.test.ts" %}
```typescript
import { fill } from "../../utility/array/fill";


describe('fill tests...', () => {

  test('method fill should return an empty array when receive an empty array', () => {
    const received: number[] = [];
    const expected = 0;

    const result = fill<number>(received, 100);

    expect(result.length).toBe(expected);
  });

  test('method fill should return the correct array when receive an array composed of number', () => {
    const received: number[] = [1, 2, 3, 4, 5];
    const expected = [1, 2, 200, 200, 200, 200, 200, 200];

    const result = fill<number>(received, 200, 2);

    result.forEach((v, i) => {
      expect(v).toBe(expected[i]);
    });
  });

  test('method fill will modify the origin array', () => {
    const received: any[] = [false, 0, '', NaN, true, function () { }];
    const expected = received;

    const result = fill(received, 'duanzhaoyang');

    expect(result).toBe(expected);
    expect(result).toBe(received);
  });

});
```
{% endcode %}

