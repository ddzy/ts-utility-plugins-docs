# \_includes

### 说明

模拟实现 `ES6` 的 `Array.includes()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/includes](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/includes)

### 用法

{% code title="\_includes.test.ts" %}
```typescript
describe('ES6Achieve._includes tests', () => {
  const _includes = ES6Achieve._includes;

  test('_includes should always return `false` when receive an empty array', () => {
    const received: number[] = [];
    const expected = false;

    const result = _includes<number>(received, 2);

    expect(result).toBe(expected);
  });

  test('_includes should return `false` when receive an array composed of `number` that no one accord with condition', () => {
    const received: number[] = [1, 2, 3, 4, 5];
    const expected = false;

    const result = _includes<number>(received, 6);

    expect(result).toBe(expected);
  });

  test('_includes should return `true` when receive an array composed of `number` that at least one accord with condition', () => {
    const received: number[] = [1, 2, 3, 4, 5];
    const expected = true;

    const result = _includes<number>(received, 3);

    expect(result).toBe(expected);
  });

  test('_includes should return `false` when receive an array composed of `object` that nobody accord with condition', () => {
    interface IPair {
      name: string;
      age: number;
    };

    const received: IPair[] = [
      { name: 'duan', age: 21 },
      { name: 'zhao', age: 31 },
      { name: 'yang', age: 41 },
    ];
    const expected = false;

    const result = _includes<IPair>(received, {
      name: 'duan',
      age: 21,
    });

    expect(result).toBe(expected);
  });

  test('_includes should return `true` when receive `NaN` and also in origin array', () => {
    const received: number[] = [1, 2, NaN, 4, 5];
    const expected = true;

    const result = _includes<number>(received, NaN);

    expect(result).toBe(expected);
  });
});
```
{% endcode %}



