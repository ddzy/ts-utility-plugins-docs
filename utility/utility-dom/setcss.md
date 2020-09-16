# setCss

### 说明

 设置单个`DOM`样式

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/setCss](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/setCss)

### 用法

{% code title="setCss.test.ts" %}
```typescript
import { setCss } from "../../utility/dom/setCss";

describe('setCss', () => {
  test('setCss should receive a DOM object and CSS Rule options, add rules to DOM.', () => {
    document.body.innerHTML = `
      <div id="app">app</div>
    `;

    setCss(
      document.getElementById('app') as HTMLElement,
      {
        color: 'red',
        'font-size': 25,
      },
    );

    expect((document.getElementById('app') as HTMLElement).getAttribute('style')).toBe('color: red; font-size: 25;');

  });
});
```
{% endcode %}

