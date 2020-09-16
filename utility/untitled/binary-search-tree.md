# binary-search-tree

### 说明

二叉搜索树

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/binary-search-tree](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/binary-search-tree)

### 用法

{% code title="binarySearchTree.test.ts" %}
```typescript
import { BinarySearchTree } from "../../utility/algorithm/binary-search-tree";

describe('BST', () => {
  const bst = new BinarySearchTree({
    nodes: [2, 5, 3, 8, 7, 4, 9, 12, 23, 10, 1],
  });

  test('bst.handleHasValue should receive a number and return true or false if the value was exist', () => {
    const received = [2, 5, 3, 8, 7, 4, 9, 12, 23, 10, 1];

    for (const v of received) {
      expect(bst.handleHasValue(v)).toBeTruthy();
    }
  });

  test('bst.handleInsert should receive a number and insert it to root', () => {
    const received = [100, 200, 300];

    for (const v of received) {
      bst.handleInsert(v);
      expect(bst.handleHasValue(v)).toBeTruthy();
    }
  });

  test('bst.handleRemove should receive a number and remove it from root', () => {
    const received = [100, 200, 300];

    for (const v of received) {
      bst.handleRemove(v);
      expect(bst.handleHasValue(v)).toBeFalsy();
    }
  });

  test('bst.handleGetDepth should return the whole tree depth when received undefined', () => {
    const expected = 6;

    expect(bst.handleGetDepth()).toBe(expected);
  });

  test('bst.handleGetDepth should receive a number and return its depth which was in tree', () => {
    const received = [5, 7, 23];
    const expected = [2, 4, 6];

    for (const [i, v] of received.entries()) {
      expect(bst.handleGetDepth(v)).toBe(expected[i]);
    }
  });

  test('bst.handleGetHeight should return whe whole tree height when received undefined', () => {
    const expected = 6;

    expect(bst.handleGetHeight()).toBe(expected);
  });

  test('bst.handleGetHeight should receive a number and return its height which was in tree', () => {
    const received = [5, 7, 23];
    const expected = [5, 1, 1];

    for (const [i, v] of received.entries()) {
      expect(bst.handleGetHeight(v)).toBe(expected[i]);
    }
  });

  test('bst.handleGetLeaves should return the collection of leaves node', () => {
    const expected = [1, 4, 7, 10, 23];
    const result = bst.handleGetLeaves();

    for (const [i, v] of result.entries()) {
      expect(v.value).toBe(expected[i]);
    }
  });

  test('bst.handleFrontOrderTraversal should ergodic the whole tree by using front-order and execute callback parameter', () => {
    const expected = [2, 1, 5, 3, 4, 8, 7, 9, 12, 10, 23];
    let count = 0;

    bst.handleFrontOrderTraversal((node) => {
      expect(node.value).toBe(expected[count]);

      count++;
    });
  });

  test('bst.handleMiddleOrderTraversal should ergodic the whole tree by using middle-order and execute callback parameter', () => {
    const expected = [1, 2, 5, 3, 4, 8, 7, 9, 12, 10, 23];
    let count = 0;

    bst.handleMiddleOrderTraversal((node) => {
      expect(node.value).toBe(expected[count]);

      count++;
    })
  });

  test('bst.handleBackOrderTraversal should ergodic the whole tree by using back-order and execute callback parameter', () => {
    const expected = [1, 5, 3, 4, 8, 7, 9, 12, 10, 23, 2];
    let count = 0;

    bst.handlBackOrderTraversal((node) => {
      expect(node.value).toBe(expected[count]);

      count++;
    })
  });

  test('bst.handleGetRoot should return the whole tree', () => {
    const expected = [2, 1, 5, 3, 4, 8, 7, 9, 12, 10, 23];
    let count = 0;

    bst.handleFrontOrderTraversal((node) => {
      expect(node.value).toBe(expected[count]);

      count++;
    });
  });

  test('bst.handleGetMaxValue should return the maximum node which was in tree', () => {
    const expected = 23;
    const result = bst.handleGetMaxValue();

    expect(result).toBe(expected);
  });

  test('bst.handleGetMinValue should return the minimum node which was in tree', () => {
    const expected = 1;
    const result = bst.handleGetMinValue();

    expect(result).toBe(expected);
  });
});
```
{% endcode %}

### API

| Name | Type | Description |
| :--- | :--- | :--- |
| handleInsert | \(value: number\) =&gt; Tree | 添加新节点 |
| handleRemove | \(value: number\) =&gt; Tree | 移除指定节点 |
| handleGetDepth | \(value?: number\) =&gt; Tree | 获取指定节点的深度 |
| handleHasValue | \(value: number\) =&gt; Tree | 查找二叉树中是否有指定的值 |
| handleFrontOrderTraversal | \(callback: \(node: TreeNode\) =&gt; void,\) =&gt; void | 先序遍历 |
| handleMiddleOrderTraversal | \(callback: \(node: TreeNode\) =&gt; void,\) =&gt; void | 中序遍历 |
| handlBackOrderTraversal | \(callback: \(node: TreeNode\) =&gt; void,\) =&gt; void | 后序遍历 |
| handleGetHeight | \(value?: number\) =&gt; number | 获取节点高度 |
| handleGetLeaves | \(\) =&gt; TreeNode\[\] | 获取叶子节点 |
| handleGetMinValue | \(\) =&gt; number \| null | 获取最小值 |
| handleGetMaxValue | \(\) =&gt; number \| null | 获取最大值 |

