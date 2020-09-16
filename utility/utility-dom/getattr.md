# getAttr

### 说明

 获取`DOM`的特定属性值

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/getAttr](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/getAttr)

### 用法

{% code title="getAttr.test.ts" %}
```typescript
import { getAttr } from "../../utility/dom/getAttr";

describe('getAttr', () => {
  test('getAttr should return null when nothing matched ', () => {
    document.body.innerHTML += `
      <input type="text" id="text" class="text" />
    `;

    expect(
      getAttr((document.getElementById('text') as HTMLElement), 'disabled')
    ).toBeNull();
  });

  test('getAttr should return the value when matched', () => {
    document.body.innerHTML = `
      <input type="text" id="text" class="text" />
    `;

    expect(getAttr(
      (document.getElementById('text') as HTMLElement),
      'type',
    )).toBe('text');
  });
});
```
{% endcode %}

