# insert-sort

### 说明

插入排序

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/sort/insert-sort](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/sort/insert-sort)

### 用法

{% code title="insertSort.test.ts" %}
```typescript
describe('Sort.insertSort tests', () => {
  const insertSort = Sort.insertSort;

  test('The method `insertSort()` should return the correct array', () => {
    const received = [
      [29, 51, 72, 68, 45, 97],
      [],
      [1, 2, 3, 4, 5],
      [3, 3, 3, 3, 3],
      [5, 4, 3, 2, 1],
      [1],
      [1045, 765, 32, 678, 98, 14, 20000],
    ];
    const expected = [
      [29, 45, 51, 68, 72, 97],
      [],
      [1, 2, 3, 4, 5],
      [3, 3, 3, 3, 3],
      [1, 2, 3, 4, 5],
      [1],
      [14, 32, 98, 678, 765, 1045, 20000],
    ];

    for (let i = 0; i < received.length; i++) {
      const result = insertSort(received[i]);

      for (let j = 0; j < result.length; j++) {
        expect(result[j]).toBe(expected[i][j]);
      }
    }
  });
});
```
{% endcode %}

