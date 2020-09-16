# \_querySelector

### 说明

 模拟实现简单的`querySelector`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/\_querySelector](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/_querySelector)

### 用法

{% code title="\_querySelector.test.ts" %}
```typescript
import { _querySelector } from "../../utility/dom/_querySelector";


describe('_querySelector', () => {
  test('_querySelector should return `null` when no matched', () => {
    document.body.innerHTML = `
      <div id="app">
        <h3 class="title">
          <p class="text"></p>
          <a class="link"></a>
        </h3>
        <section class="post">
          <p class="text"></p>
        </section>
      </div>
    `;

    const received = ['.ddzy', 'ddzy', '#ddzy', ''];

    for (const v of received) {
      expect(_querySelector(v)).toBeNull();
    }
  });

  test('_querySelector should return `a single Element` when matched', () => {
    document.body.innerHTML = `
      <div id="app">
        <h3 class="title">
          <p class="text"></p>
          <a class="link"></a>
        </h3>
        <section class="post">
          <p class="text"></p>
        </section>
      </div>
    `;

    const received = ['#app', '.title', '.text', 'a'];
    const expected = [
      document.querySelector('#app'),
      document.querySelector('.title'),
      document.querySelector('.text'),
      document.querySelector('a'),
    ];

    for (const [i, v] of received.entries()) {
      expect(_querySelector(v)).toBe(expected[i]);
    }
  });
});
```
{% endcode %}

