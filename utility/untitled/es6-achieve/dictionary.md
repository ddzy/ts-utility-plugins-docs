# Dictionary

### 说明

模拟实现 `ES6` 的 `Map` 数据结构

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/dictionary](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/dictionary)

### 用法

{% code title="dictionary.test.ts" %}
```typescript
describe('ES6Achieve.Dictionary tests', () => {
  const map = new ES6Achieve.Dictionary();

  test('Dictionary should work friendly', () => {
    const str1 = 'duanzhaoyang';
    const num1 = 19980808;
    const bool1 = true;
    const arr1 = [1, 2, 3];
    const obj1 = { skill: 'program' };
    const func1 = function () { };

    const obj2 = { name: 'duan', age: 21 };

    // map.set()
    map.set(str1, str1);
    map.set(num1, num1);
    map.set(bool1, bool1);
    map.set(arr1, arr1);
    map.set(obj1, obj1);
    map.set(func1, func1);

    expect(map.size()).toBe(6);

    // map.set() -> for twice
    map.set(bool1, false);
    map.set(obj1, obj2);

    expect(map.size()).toBe(6);

    // map.set() => for three times
    map.set([], []);

    expect(map.size()).toBe(7);

    // map.get()
    expect(map.get(arr1)).toBe(arr1);
    expect(map.get(obj1)).toBe(obj2);

    expect(map.size()).toBe(7);

    // map.delete()
    expect(map.delete(bool1)).toBeTruthy();
    expect(map.size()).toBe(6);

    // map.traversal()
    map.traversal(function (value, key) {
      expect(this).toBe(map);

      if (key === bool1) {
        return false;
      }
    });
  });
});
```
{% endcode %}



