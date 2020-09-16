# setAttr

### 说明

 设置单个`DOM`属性

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/setAttr](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/setAttr)

### 用法

{% code title="setAttr.test.ts" %}
```typescript
import { setAttr } from "../../utility/dom/setAttr";

describe('setAttr', () => {
  test('setAttr should receive a DOM object and attributes, add attributes to DOM, and return nothing', () => {
    document.body.innerHTML = `
      <input id="text"></div>
    `;

    expect(setAttr(
      document.getElementById('text') as HTMLElement,
      {
        class: 'text',
        type: 'text',
      }
    ));
  });
});
```
{% endcode %}

