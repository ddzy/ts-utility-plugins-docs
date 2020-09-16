# curry

### 说明

函数柯里化

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/curry](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/curry)

### 用法

{% code title="curry.test.ts" %}
```typescript
import { curry } from "../../utility/function/curry";

describe('curry() tests...', () => {
  test('method curry should works normally', () => {
    const received = function (a: number, b: number, c: number, d: number) {
      return a + b + c + d;
    }

    const curriedFunc = curry(received);

    expect(curriedFunc(1, 2, 3)(4)).toBe(10);
    expect(curriedFunc(100)(200)(300)(400)).toBe(1000);
    expect(curriedFunc(23)(34, 45)(56)).toBe(158);
  });
});
```
{% endcode %}

