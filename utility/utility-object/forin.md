# forIn

### 说明

使用 `iteratee` 遍历对象的自身和继承的可枚举属性. `iteratee` 会传入3个参数: \(value, key, object\). 如果返回 `false`, iteratee 会提前退出遍历.

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/forIn](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/forIn)

### 用法

{% code title="forIn.test.ts" %}
```typescript
import { forIn } from "../../utility/object/forIn";

describe('forIn tests...', () => {

  test('method forIn should not exit', () => {
    interface IReceivedProps {
      name: string,
      age: number,
      skill: string,
    };

    const received: IReceivedProps = {
      name: 'duanzhaoyang',
      age: 21,
      skill: 'program',
    };
    const expected = received;

    forIn(received, (value, key) => {
      expect(value).toBe(expected[key as keyof typeof expected]);
    });
  });

  test('method forIn should exit when return `false`', () => {
    interface IReceivedProps {
      city: string[];
      position: {
        x: number,
        y: number,
      };
      continue: boolean;
      nextOne: number;
      nextTwo: number;
    };

    const received: IReceivedProps = {
      city: ['Dongguan', 'Foshan', 'Guangzhou'],
      position: {
        x: 100,
        y: 200,
      },
      continue: false,
      nextOne: 1,
      nextTwo: 2,
    };

    const expected = received;
    let count = 0;

    forIn<IReceivedProps>(received, function (value, key, origin) {
      count++;
      expect(value).toBe(expected[key as keyof typeof expected]);
      expect(this).toBe(origin);

      if (key === 'continue') {
        return false;
      }
    });

    expect(count).toBe(3);
  });

});
```
{% endcode %}

