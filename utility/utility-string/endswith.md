# endsWith

### 说明

 检查字符串`text`是否以给定的`target`字符串结尾

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/endsWith](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/endsWith)

### 用法

{% code title="endsWith.test.ts" %}
```typescript
import { endsWith } from "../../utility/string/endsWith";

describe('endsWith tests...', () => {

  test('endsWith should return the correct value', () => {
    interface IReceivedParams {
      text: string;
      target: string;
      position: number | undefined;
    };

    const received: IReceivedParams[] = [
      {
        text: 'duanzhaoyang',
        target: 'a',
        position: 3,
      },
      {
        text: 'duanzhaoyang',
        target: 'ao',
        position: undefined,
      },
      {
        text: 'ddzy',
        target: 'y',
        position: undefined,
      },
      {
        text: 'duan',
        target: 'd',
        position: 4,
      },
    ];
    const expected = [true, false, true, true];

    received.forEach((v, i) => {
      const result = endsWith(v.text, v.target, v.position);

      expect(result).toBe(expected[i]);
    });
  });

});
```
{% endcode %}

