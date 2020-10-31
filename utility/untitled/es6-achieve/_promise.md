# \_Promise

### 说明

模拟实现 `ES6` 的 `Promise`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/promise](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/promise)

### 用法

{% code title="\_Promise.test.ts" %}
```typescript
describe('ES6Achieve._Promise tests', () => {
  const _Promise = ES6Achieve._Promise;

  test('_Promise should work fine', () => {
    const result1 = new _Promise((resolve) => {
      setTimeout(() => {
        resolve(1);
      }, 0);
    });
    result1.then((value) => {
      expect(value).toBe(1);

      return value + 1;
    }).then((value) => {
      expect(value).toBe(2);
    });

    const result2 = new _Promise((resolve) => {
      resolve(100);
    });
    result2.then((value) => {
      expect(value).toBe(100);

      return value / 5;
    }).then((value) => {
      expect(value).toBe(20);
    });
  });
});
```
{% endcode %}



