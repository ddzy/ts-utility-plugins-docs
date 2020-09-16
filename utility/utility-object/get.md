# get

### 说明

  根据`object`对象的`path`路径获取值

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/get](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/get)

### 用法

{% code title="get.test.ts" %}
```typescript
import { get } from "../../utility/object/get";

describe('get() tests...', () => {

  test('method get should return the correct value', () => {
    const received: Array<{
      origin: any,
      path: string | string[],
      defaultValue: any,
    }> = [
        {
          origin: {},
          path: 'a.b.c',
          defaultValue: undefined,
        },
        {
          origin: {},
          path: 'a[0].b[1].c',
          defaultValue: 'default',
        },
        {
          origin: {
            a: [
              {
                b: {
                  c: 3,
                },
              },
            ],
          },
          path: 'a[0].b.c',
          defaultValue: undefined,
        },
        {
          origin: [
            {
              a: [
                {
                  b: 1998,
                },
              ],
            },
          ],
          path: ['0', 'a', '0', 'b'],
          defaultValue: undefined,
        },
      ];
    const expected = [undefined, 'default', 3, 1998];

    received.forEach((v, i) => {
      const result = get(v.origin, v.path, v.defaultValue);

      expect(result).toBe(expected[i]);
    });
  });
});
```
{% endcode %}

