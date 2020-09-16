# \_every

### 说明

模拟实现 `ES6` 的 `Array.every()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/every](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/every)

### 用法

{% code title="\_every.test.ts" %}
```typescript
describe('ES6Achieve._every tests', () => {
  const _every = ES6Achieve._every;

  test('_every should always return `true` when receive an empty array', () => {
    const received: number[] = [];
    const expected = true;

    const result = _every<number>(received, (v) => {
      return v > 0;
    });

    expect(result).toBe(expected);
  });

  test('_every should return `true` when receive an array composed of `number` that accord with condition', () => {
    const received: number[] = [1, 2, 3, 4, 5];
    const expected = true;

    const result = _every<number, null>(received, (v) => {
      return v < 10;
    });

    expect(result).toBe(expected);
  });

  test('_every should return `false` when receive an array composed of `object` that not accord with condition', () => {
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

    const result = _every<IPair, null>(received, (v) => {
      return v.age < 0;
    });

    expect(result).toBe(expected);
  });

  test('_every should called by custom `this` context', () => {
    const context = {
      name: 'ddzy',
      printName() {
        return this.name;
      },
    };

    const received: number[] = [1, 2, 3, 4, 5];
    const expected = {
      context,
      result: true,
    };

    const result = _every<number, typeof context>(received, function (v) {
      expect(this).toBe(expected.context);

      return v < 6;
    }, context);

    expect(result).toBe(expected.result);
  });
});
```
{% endcode %}



