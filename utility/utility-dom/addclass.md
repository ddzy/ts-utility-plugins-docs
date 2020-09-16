# addClass

### 说明

 获取`DOM`的特定属性值

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/addClass](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/addClass)

### 用法

{% code title="addClass.test.ts" %}
```typescript
import { addClass } from "../../utility/dom/addClass";

describe('addClass', () => {
  test('addClass should add the class to a DOM object', () => {
    document.body.innerHTML = `
      <div id="app" class="c1"></div>
    `;

    addClass(
      (document.getElementById('app') as HTMLElement),
      'c2',
    );

    expect((document.getElementById('app') as HTMLElement).classList.contains('c2')).toBeTruthy();
  });
});
```
{% endcode %}

