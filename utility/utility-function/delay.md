# delay

### 说明

 延迟`wait`毫秒后执行处理器`callback`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/delay](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/delay)

### 用法

{% code title="delay.test.ts" %}
```typescript
import { delay } from "../../utility/function/delay";

describe('delay', () => {
  test('delay should fire the callback after wait ms', () => {
    const received = function () {
      expect(true).toBeTruthy();
    }

    delay(received, 500);
  });

  test('delay should receive params that passed', () => {
    const received = function (name: string, age: number) {
      expect(name).toBe('ddzy');
      expect(age).toBe(21);
    }

    delay(received, 1000, 'ddzy', 21);
  });

  test('delay should return the timeout id', () => {
    const received = function () {
      expect(true).toBeTruthy();
    }

    const result = delay(received, 1500);

    expect(typeof result).toBe('number');
  });
});
```
{% endcode %}

