# forOwn

### 说明

 遍历对象自身的可枚举属性, 不包括继承而来的属性

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/forOwn](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/forOwn)

### 用法

{% code title="forOwn.test.ts" %}
```typescript
import { forOwn } from "../../utility/object/forOwn";

describe('forOwn tests...', () => {
  test('method forOwn should traversal the object with its own property', () => {
    const received = {
      name: 'duanzhaoyang',
      age: 21,
      address: 'Dongguan',
    };
    const expected = {
      name: 'duanzhaoyang',
      age: 21,
      address: 'Dongguan',
    };

    forOwn<typeof received>(received, (key, value, origin) => {
      expect(expected[key as keyof typeof expected]).toBe(value);
      expect(origin).toBe(received);
    });
  });

  test('method forOwn should traversal the object without the property which were  inherite by prototype', () => {
    class Received {
      public name: string = '';
      public age: number = 0;
    }
    Received.prototype.isCorrect = false;
    const expected = {
      name: '',
      age: 0,
    };

    const received = new Received();

    forOwn(received, (key, value, origin) => {
      expect(expected[key as keyof typeof expected]).toBe(value);
      expect(key !== 'isCorrect').toBeTruthy();
      expect(origin).toBe(received);
    });
  });
});
```
{% endcode %}

