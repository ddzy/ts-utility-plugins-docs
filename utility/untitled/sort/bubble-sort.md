# bubble-sort

### 说明

冒泡排序

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/sort/bubble-sort](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/sort/bubble-sort)

### 用法

{% code title="bubbleSort.test.ts" %}
```typescript
const bubbleSort = Sort.bubbleSort;

test('The method `bubbleSort()` should return the correct array', () => {
  const received = [
    [29, 51, 72, 68, 45, 97],
    [],
    [1, 2, 3, 4, 5],
    [3, 3, 3, 3, 3],
    [5, 4, 3, 2, 1],
    [1]
  ];
  const expected = [
    [29, 45, 51, 68, 72, 97],
    [],
    [1, 2, 3, 4, 5],
    [3, 3, 3, 3, 3],
    [1, 2, 3, 4, 5],
    [1]
  ];

  for (let i = 0; i < received.length; i++) {
    const result = bubbleSort(received[i]);

    for (let j = 0; j < result.length; j++) {
      expect(result[j]).toBe(expected[i][j]);
    }
  }
});
```
{% endcode %}

