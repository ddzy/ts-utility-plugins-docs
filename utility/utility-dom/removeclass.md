# removeClass

### 说明

 移除指定`DOM`的单个类名

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/removeClass](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/removeClass)

### 用法

{% code title="removeClass.test.ts" %}
```typescript
import { removeClass } from "../../utility/dom/removeClass";

describe('removeClass', () => {
  test('removeClass should remove the class from a DOM object', () => {
    document.body.innerHTML = `
      <div id="app" class="c1 c2"></div>
    `;

    removeClass(
      (document.getElementById('app') as HTMLElement),
      'c2',
    );

    expect(
      (document.getElementById('app') as HTMLElement).classList.contains('c2')
    ).toBeFalsy();
  });
});
```
{% endcode %}

