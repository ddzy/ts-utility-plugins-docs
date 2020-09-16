# \_filter

### 说明

模拟实现 `ES6` 的 `Array.filter()` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/filter](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/filter)

### 用法

{% code title="\_filter.test.ts" %}
```typescript
describe('ES6Achieve._filter tests', () => {
  const _filter = ES6Achieve._filter;

  test('_filter should return a new empty array when receive an empty array', () => {
    const received: number[] = [];

    const result = _filter<number>(received, (v) => {
      return !!v;
    });

    expect(result.length).toBe(0);
    received.push(2);
    received.push(3);
    expect(received.length).toBe(2);
    expect(result.length).toBe(0);
  });

  test('_filter should return the eligible array when receive an array composed of number', () => {
    const received: number[] = [1, 2, 3, 4, 5, 6, 7, 8];
    const expected: number[] = [2, 4, 6, 8];

    const result = _filter<number>(received, (v) => {
      return v % 2 === 0;
    });

    for (const [i, v] of result.entries()) {
      expect(v).toBe(expected[i]);
    }
  });

  test('_filter should return the eligible array when receive an array composed of plain object', () => {
    interface User {
      name: string,
      age: number,
    };
    const received: User[] = [
      { name: 'duan', age: 20 },
      { name: 'zhao', age: 30 },
      { name: 'yang', age: 40 },
    ];
    const expected: User[] = [
      { name: 'zhao', age: 30 },
      { name: 'yang', age: 40 },
    ];

    const result = _filter<User>(received, (v) => {
      return v.age >= 30;
    });

    for (const [i, v] of result.entries()) {
      expect(v.name).toBe(expected[i].name);
      expect(v.age).toBe(expected[i].age);
    }
  });

  test('_filter should return the aligible array and print the truthy context when receive an array composed of number', () => {
    interface Obj {
      secret: string,
      say: (secret: string) => void,
    };

    const obj: Obj = {
      secret: '980808',
      say() {
        console.log(this.secret);
      },
    };
    const received = [-1, 1, -2, 2, -3, 3];
    const expected = {
      context: obj,
      arr: [1, 2, 3],
    };

    const result = _filter<number, Obj>(received, function (v) {
      expect(this).toBe(expected.context);

      return v > 0;
    }, obj);

    for (const [i, v] of result.entries()) {
      expect(v).toBe(expected.arr[i]);
    }
  });
});
```
{% endcode %}



