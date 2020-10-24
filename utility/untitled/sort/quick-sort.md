# quick-sort

### 说明

快速排序\(`递归`\)

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/sort/quick-sort](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/sort/quick-sort)

### 用法

{% code title="quickSort.test.ts" %}
```typescript
describe('Sort.quickSort tests', () => {
  const quickSort = Sort.quickSort;

  test('The method `quickSort()` should return the correct array', () => {
    const received = [
      [49, 38, 65, 97, 76, 13, 27, 49, 55, 4],
      [],
      [1, 2, 3, 4, 5],
      [3, 3, 3, 3, 3],
      [5, 4, 3, 2, 1],
      [1],
      [1045, 765, 32, 678, 98, 14, 20000],
    ];
    const expected = [
      [4, 13, 27, 38, 49, 49, 55, 65, 76, 97],
      [],
      [1, 2, 3, 4, 5],
      [3, 3, 3, 3, 3],
      [1, 2, 3, 4, 5],
      [1],
      [14, 32, 98, 678, 765, 1045, 20000],
    ];

    for (let i = 0; i < received.length; i++) {
      const result = quickSort(received[i]);

      for (let j = 0; j < result.length; j++) {
        expect(result[j]).toBe(expected[i][j]);
      }
    }
  });
});

```
{% endcode %}

