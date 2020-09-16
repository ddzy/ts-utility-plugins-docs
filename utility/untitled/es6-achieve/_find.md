# \_find

### 说明

模拟实现 `ES6` 的 `Array.find()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/find](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/find)

### 用法

{% code title="\_find.test.ts" %}
```typescript
describe('ES6Achieve._find tests', () => {
  const _find = ES6Achieve._find;

  test('_every should always return `undefined` when receive an empty array', () => {
    const received: number[] = [];
    const expected = undefined;

    const result = _find<number>(received, (v) => {
      return v > 0;
    });

    expect(result).toBe(expected);
  });

  test('_every should return first value that has been found when receive an array composed of `number`', () => {
    const received: number[] = [-1, -2, 1, 2, 3];
    const expected = 1;

    const result = _find<number, null>(received, (v) => {
      return v > 0;
    });

    expect(result).toBe(expected);
  });

  test('_every should return the first that has been found when receive an array composed of `object`', () => {
    interface IPair {
      name: string;
      age: number;
    };

    const received: IPair[] = [
      { name: 'duan', age: 21 },
      { name: 'zhao', age: 31 },
      { name: 'yang', age: 41 },
    ];
    const expected = received[1];

    const result = _find<IPair, null>(received, (v) => {
      return v.age >= 31;
    });

    expect(result).toBe(expected);
  });

  test('_every should called by custom `this` context', () => {
    const context = {
      secret: 'duanzhaoyang',
      printSecret() {
        return this.secret;
      },
    };

    const received: number[] = [1, 2, 3, 4, 5];
    const expected = {
      context,
      result: 5,
    };

    const result = _find<number, typeof context>(received, function (v) {
      expect(this).toBe(expected.context);

      return v === 5;
    }, context);

    expect(result).toBe(expected.result);
  });
});
```
{% endcode %}



