# capitalize

### 说明

 将指定的字符串的`首字母`大写, 剩下为小写

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/capitalize](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/capitalize)

### 用法

{% code title="capitalize.test.ts" %}
```typescript
import { capitalize } from "../../utility/string/capitalize";

describe('capitalize tests...', () => {
  test('capitalize should return the origin text when receive an empty string', () => {
    const received = '';
    const expected = '';

    const result = capitalize(received);

    expect(result).toBe(expected);
  });

  test('capitalize should return the converted string correctly', () => {
    const received = ['ZHAO', 'duan'];
    const expected = ['Zhao', 'Duan'];

    const result = received.map((v) => {
      return capitalize(v);
    });

    result.forEach((v, i) => {
      expect(v).toBe(expected[i]);
    });
  });

  test('capitalize should return the converted string when receive a text contains special characters', () => {
    const received = ['_DDZY', '___&*duanzhaoYANg'];
    const expected = ['_Ddzy', '___&*Duanzhaoyang'];

    const result = received.map((v) => {
      return capitalize(v);
    });

    result.forEach((v, i) => {
      expect(v).toBe(expected[i]);
    });
  });
});
```
{% endcode %}

