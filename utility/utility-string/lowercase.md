# lowerCase

### 说明

 转换字符串`string`以空格分开单词, 并转换为`小写`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/lowerCase](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/lowerCase)

### 用法

{% code title="lowerCase.test.ts" %}
```typescript
import { lowerCase } from "../../utility/string/lowerCase";

describe('lowerCase tests...', () => {

  test('lowerCase should return `` when receive an empty string', () => {
    const received = '';
    const expected = '';

    const result = lowerCase(received);

    expect(result).toBe(expected);
  });

  test('lowerCase should return the converted string correctly', () => {
    const received = ['--Duan-Zhao--', 'alioeDuan', '__DUAN_ZHAO_YANG__'];
    const expected = ['duan zhao', 'alioeduan', 'duan zhao yang'];

    received.forEach((v, i) => {
      const result = lowerCase(v);

      expect(result).toBe(expected[i]);
    });
  });

});
```
{% endcode %}

