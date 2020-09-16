# traversalDOMWithBFS

### 说明

 `BFS`遍历指定`DOM`节点

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/traversalDOMWithBFS](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/traversalDOMWithBFS)

### 用法

{% code title="traversalDOMWithBFS.test.ts" %}
```typescript
import { traversalDOMWithBFS } from "../../utility/dom/traversalDOMWithBFS";

describe('traversalDOMWithBFS', () => {
  test('traversalDOMWithBFS should traversal DOM Tree by BFS', () => {
    document.body.innerHTML = `
      <div id="app">
        <h3 class="title">title</h3>
        <section class="post">
          <p class="text"></p>
        </section>
      </div>
    `;

    const expected = [
      (document.getElementById('app') as HTMLDivElement),
      (document.querySelector('.title') as HTMLTitleElement),
      (document.querySelector('.post') as HTMLDivElement),
      (document.querySelector('.text') as HTMLParagraphElement),
    ];
    const result: HTMLElement[] = [];

    traversalDOMWithBFS(
      (document.getElementById('app') as HTMLElement),
      (node) => {
        result.push(node);
      }
    );

    for (const [index, node] of result.entries()) {
      expect(node).toBe(expected[index]);
    }
  });
});
```
{% endcode %}

