# toFlatArrayOutPlace

### 说明

 数组扁平化\(`非原地算法`\)

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/toFlatArrayOutPlace](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/toFlatArrayOutPlace)

### 用法

{% code title="toFlatArrayOutPlace.test.ts" %}
```typescript
import { toFlatArrayOutPlace } from "../../utility/array/toFlatArrayOutPlace";

describe('toFlatArrayOutPlace', () => {
  test('toFlatArrayOutPlace should flatten the origin array', () => {
    const received = [
      'duan',
      1998,
      [
        'a',
        'b',
        [
          'c',
          'd',
          [
            'e',
            'f',
            123
          ],
        ],
      ],
      {
        name: 'duan',
        age: 20,
      },
    ];
    const expected = [
      'duan',
      1998,
      'a',
      'b',
      'c',
      'd',
      'e',
      'f',
      123,
      { name: 'duan', age: 20 },
    ];

    const result = toFlatArrayOutPlace(received);

    for (const [outerI, outerV] of result.entries()) {
      expect(outerV).toEqual(expected[outerI]);
    }
  });
});
```
{% endcode %}

