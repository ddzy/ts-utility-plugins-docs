# \_startsWith

### 说明

模拟实现 `ES6` 的 `String.startsWith()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/startsWith](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/startsWith)

### 用法

{% code title="\_startsWith.test.ts" %}
```typescript
describe('ES6Achieve._startsWith tests', () => {
  const _startsWith = ES6Achieve._startsWith;

  test('_startsWith should return whether the `origin` string is composed of `target`', () => {
    const origin = 'ddzy';
    const received = ['d', 'yang', 'ddzyy'];
    const expected = [true, false, false];

    for (const [i, v] of received.entries()) {
      const result = _startsWith(origin, v);

      expect(result).toBe(expected[i]);
    }
  });

  test('_startsWith should return whether the `origin` string is composed of `target` at special `index`', () => {
    const origin = 'ddzy';
    const received = ['ddz', 'dzy'];
    const expected = [false, false];

    for (const [i, v] of received.entries()) {
      const result = _startsWith(origin, v, 1);

      expect(result).toBe(expected[i]);
    }
  });
});
```
{% endcode %}



