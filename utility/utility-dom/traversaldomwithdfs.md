# traversalDOMWithDFS

### 说明

 `DFS`遍历指定`DOM`节点

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/traversalDOMWithDFS](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/dom/traversalDOMWithDFS)

### 用法

{% code title="traversalDOMWithDFS.test.ts" %}
```typescript
import { traversalDOMWithDFS } from "../../utility/dom/traversalDOMWithDFS";

describe('traversalDOMWithDFS', () => {
  test('traversalDOMWithDFS should traversal DOM Tree by DFS', () => {
    document.body.innerHTML = `
      <div id="app">
        <h3 class="title">
          <a class="link"></a>
        </h3>
        <section class="post">
          <p class="text"></p>
        </section>
      </div>
    `;

    const expected = [
      (document.getElementById('app') as HTMLDivElement),
      (document.querySelector('.title') as HTMLTitleElement),
      (document.querySelector('.link') as HTMLAnchorElement),
      (document.querySelector('.post') as HTMLDivElement),
      (document.querySelector('.text') as HTMLParagraphElement),
    ];
    const result: HTMLElement[] = [];

    traversalDOMWithDFS(
      (document.getElementById('app') as HTMLElement),
      (node) => {
        result.push(node);
      }
    );

    for (const [index, node] of result.entries()) {
      expect(node).toBe(expected[index]);
    }
  })
})
```
{% endcode %}

