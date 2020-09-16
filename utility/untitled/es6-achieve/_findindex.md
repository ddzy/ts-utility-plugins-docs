# \_findIndex

### 说明

模拟实现 `ES6` 的 `Array.findIndex()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/findIndex](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/findIndex)

### 用法

{% code title="\_findIndex.test.ts" %}
```typescript
describe('ES6Achieve._findIndex tests', () => {
  const _findIndex = ES6Achieve._findIndex;

  test('_findIndex should always return `-1` when receive an empty array', () => {
    const received: number[] = [];
    const expected = -1;

    const result = _findIndex<number>(received, (v) => {
      return v > 0;
    });

    expect(result).toBe(expected);
  });

  test('_findIndex should return `-1` when not found', () => {
    const received: number[] = [23, 4, 56, 73, 1];
    const expected = -1;

    const result = _findIndex<number>(received, (v) => {
      return v < 0;
    });

    expect(result).toBe(expected);
  });

  test('_findIndex should return the place of the first value which was eligible', () => {
    const received: number[] = [444, 45, -4, 78, -5];
    const expected = 2;

    const result = _findIndex<number>(received, (v) => {
      return v < 0;
    });

    expect(result).toBe(expected);
  });

  test('_findIndex should be called by custom `context`', () => {
    const context = {
      secret: 'ddzy',
    };

    const received: number[] = [45, 2, 1, 33, -5];
    const expected = {
      place: 0,
      context,
    };

    const result = _findIndex<number, typeof context>(received, function (v) {
      expect(this).toBe(expected.context);

      return v > 40;
    }, context);

    expect(result).toBe(expected.place);
  });
});
```
{% endcode %}



