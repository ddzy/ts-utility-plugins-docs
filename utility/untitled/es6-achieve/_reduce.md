# \_reduce

### 说明

模拟实现 `ES6` 的 `Array.reduce()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/reduce](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/reduce)

### 用法

{% code title="\_reduce.test.ts" %}
```typescript
describe('ES6Achieve._reduce tests', () => {
  const _reduce = ES6Achieve._reduce;

  test('_reduce should return `undefined` when received an empty array', () => {
    const received: any[] = [];

    const result = _reduce(received, (total, current) => {
      return total + current;
    });

    expect(result).toBeUndefined();
  });

  test('_reduce should return `number` when received an array being composed of `number`', () => {
    const received = [1, 2, 3, 4, 5];
    const expected = 15;

    const result = _reduce<number, number>(received, (total, current) => {
      return total + current;
    });

    expect(result).toBe(expected);
  });

  test('_reduce should return `number` when received an array being composed of `number` and an `initialValue`', () => {
    const received = [1, 2, 3, 4, 5];
    const expected = 25;

    const result = _reduce<number, number>(received, (total, current) => {
      return total + current;
    }, 10);

    expect(result).toBe(expected);
  });

  test('_reduce should return `number` when received an array being composed of `object`', () => {
    const received = [
      { uuid: 1, name: 'duan', age: 10 },
      { uuid: 2, name: 'duan', age: 20 },
      { uuid: 3, name: 'duan', age: 30 },
    ];
    const expected = 60;

    const result = _reduce<typeof received[0], number>(received, (total, current) => {
      return total + current.age;
    }, 0);

    expect(result).toBe(expected);
  });

  test('_reduce should return `string` when received an array being composed of `number`', () => {
    const received = [1, 2, 3, 4, 5];
    const expected = '12345';

    const result = _reduce<number, string>(received, (total, current) => {
      return total + current;
    }, '');

    expect(result).toBe(expected);
  });
});
```
{% endcode %}



