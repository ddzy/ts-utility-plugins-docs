# convertPairToCSSText

### 说明

 将给定的`CSS`样式键值对转化为`cssText`字符串

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/convertPairToCSSText](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/convertPairToCSSText)

### 用法

{% code title="convertPairToCSSText.test.ts" %}
```typescript
import { convertPairToCSSText } from "../../utility/dom/convertPairToCSSText";

describe('convertPairToCSSText', () => {
  test('convertPairToCSSText should extract CSS pair object into truthy cssText.', () => {
    const origin: Partial<CSSStyleDeclaration> = {
      border: '1px dotted red',
      backgroundColor: 'blue',
    };
    const expected = `border: 1px dotted red; background-color: blue; `;

    expect(convertPairToCSSText(origin)).toBe(expected);
  });
});
```
{% endcode %}

