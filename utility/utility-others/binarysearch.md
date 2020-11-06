# binarySearch

### 说明

 简单实现二分查找算法

### 源码

[https://github.com/ddzy/ts-utility-plugins/blob/master/src/ddzy/utility/others/binarySearch/index.ts](https://github.com/ddzy/ts-utility-plugins/blob/master/src/ddzy/utility/others/binarySearch/index.ts)

### 用法

{% code title="binarySearch.test.ts" %}
```typescript
import binarySearch from "../../utility/others/binarySearch";

describe('binarySearch tests...', () => {
  test('The method named `binarySearch() should return a correct index value', () => {
    const arr = [10, 867, 4, 34, 9, 98, 45, 67];
    const received = [
      {
        arr,
        value: 34,
      },
      {
        arr,
        value: 99,
      },
    ];
    const expected = [3, -1];

    for (const [key, value] of received.entries()) {
      const result = binarySearch(value.arr, value.value);

      expect(result).toBe(expected[key]);
    }
  });
});
```
{% endcode %}

