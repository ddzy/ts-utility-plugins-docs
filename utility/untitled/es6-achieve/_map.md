# \_map

### 说明

模拟实现 `ES6` 的 `Array.map()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/map](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/map)

### 用法

{% code title="\_map.test.ts" %}
```typescript
describe('ES6Achieve._map tests', () => {
  const _map = ES6Achieve._map;

  test('_map should handle each of value which were in `source array` with `callback`', () => {
    const received = [
      [1, 2, 3, 4, 5, 6],
      [24, 42, 4, 1, 2, 9, 58],
    ];
    const expected = [
      [2, 4, 6, 8, 10, 12],
      [48, 84, 8, 2, 4, 18, 116],
    ];

    for (const [outerI, outerV] of received.entries()) {
      const result = _map<number, number>(
        outerV,
        (outerVV) => {
          return outerVV * 2;
        },
      );

      for (const [innerI, innerV] of result.entries()) {
        expect(innerV).toBe(expected[outerI][innerI]);
      }
    }
  });

  test('_map should handle `callback` with customized `this` context', () => {
    interface IContext {
      name: string,
      age: number,
    };
    const context: IContext = {
      name: 'ddzy',
      age: 21,
    };

    const received = [
      ['', 'd', 'dd', 'ddz', 'ddzy'],
    ];
    const expected = [
      [' 980808', 'd 980808', 'dd 980808', 'ddz 980808', 'ddzy 980808'],
    ];

    for (const [outerI, outerV] of received.entries()) {
      const result = _map<string, string, IContext>(
        outerV,
        (outerVV, _outerII, __this__) => {
          // ? test `this` context
          expect(__this__).toBe(context);

          return outerVV + ' 980808';
        },
        context,
      );

      for (const [innerI, innerV] of result.entries()) {
        expect(innerV).toBe(expected[outerI][innerI]);
      }
    }
  });

  test('_map should return a `new` array and cannot modify the `origin` array', () => {
    interface IContext {
      uuid: number,
      age: number,
    };

    const received = [
      [
        { uuid: 1, age: 10 },
        { uuid: 2, age: 20 },
        { uuid: 3, age: 30 },
      ],
    ];
    const expected = [
      [
        { uuid: 1, age: 110 },
        { uuid: 2, age: 120 },
        { uuid: 3, age: 130 },
      ],
    ];

    for (const [outerI, outerV] of received.entries()) {
      const result = _map<IContext, IContext>(
        outerV,
        (outerVV) => {
          return {
            uuid: outerVV.uuid,
            age: outerVV.age + 100,
          };
        },
      );

      for (const [innerI, innerV] of result.entries()) {
        expect(innerV.uuid).toBe(expected[outerI][innerI].uuid);
        expect(innerV.age).toBe(expected[outerI][innerI].age);
      }

      // ?
      result.push({
        uuid: 4,
        age: 140,
      });
      expect(outerV.length).toBe(3);
      expect(result.length).toBe(4);
    }
  });
```
{% endcode %}



