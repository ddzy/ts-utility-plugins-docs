# eq

### 说明

 比较两个值是否全等\(`NaN`为`true`\)

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/eq](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/eq)

### 用法

{% code title="eq.test.ts" %}
```typescript
import { eq } from "../../utility/others/eq";

describe('eq tests: ', () => {
  test('eq should return true or false when receive two basic value that equals', () => {
    const received = [100, 100];
    const expected = true;

    const result = eq(received[0], received[1]);

    expect(result).toBe(expected);
  });

  test('eq should return false when receive two object but point at different memory', () => {
    const received = [{}, {}];
    const expected = false;

    const result = eq(received[0], received[1]);

    expect(result).toBe(expected);
  });

  test('eq should return true when receive two object point at same memory', () => {
    const obj = {};

    const received = [obj, obj];
    const expected = true;

    const result = eq(received[0], received[1]);

    expect(result).toBe(expected);
  });

  test('eq should return true when receive two NaN value', () => {
    const received = [NaN, NaN];
    const expected = true;

    const result = eq(received[0], received[1]);

    expect(result).toBe(expected);
  });
});
```
{% endcode %}

