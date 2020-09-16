# \_reflect

### 说明

模拟实现 `ES6` 的 `Reflect` 方法

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/reflect](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/es6-achieve/reflect)

### 用法

{% code title="\_reflect.test.ts" %}
```typescript
describe('ES6Achieve._reflect tests', () => {
  const _reflect = ES6Achieve._reflect;

  test('_reflect.get should return the value of the special key from target object', () => {
    const obj = {
      name: 'ddzy',
      age: 21,
    };
    const received = [
      'name',
      0,
      'skill',
    ];
    const expected = [
      'ddzy',
      undefined,
      undefined,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.get(obj, v);
      expect(temp).toBe(expected[i]);
    }
  });

  test('_reflect.set should set the new value to the designative key', () => {
    const obj = {
      name: 'ddzy',
      age: 21,
    };
    const received = [
      {
        key: 'skill',
        value: 'program',
      },
      {
        key: 'hobby',
        value: ['run', 'play-game'],
      },
    ];
    const expected = [
      true,
      true,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.set(obj, v.key, v.value);
      expect(temp).toBe(expected[i]);
    }

    expect(obj['skill' as keyof typeof obj]).toBe('program');
    expect(Array.isArray(obj['hobby' as keyof typeof obj])).toBeTruthy();
  });

  test('_reflect.has should return `true` when the designative key was in target object, otherwise `false`', () => {
    const obj = {
      name: 'ddzy',
      age: 21,
    };
    const received = [
      'name',
      'age',
      'skill',
      'hobby',
    ];
    const expected = [
      true,
      true,
      false,
      false,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.has(obj, v);
      expect(temp).toBe(expected[i]);
    }
  });

  test('_reflect.apply should be called same as native API named `apply`', () => {
    const obj = {
      name: 'ddzy',
      age: 21,
    };
    function func1() {
      return 'Hello world';
    }
    function func2(...args: any[]) {
      return args[0];
    }
    function func3() {
      return this;
    }
    const received = [
      func1,
      func2,
      func3,
    ];
    const expected = [
      'Hello world',
      'Hello ddzy',
      obj,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.apply(v, obj, ['Hello ddzy']);
      expect(temp).toBe(expected[i]);
    }
  });

  test('_reflect.construct should return the `instance` of the designative function', () => {
    function Person1() { }
    const Person2 = () => { };

    const received = [
      Person1,
      Person2,
    ];
    const expected = [
      true,
      true,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.construct(v, []);
      expect(temp instanceof v).toBe(expected[i]);
    }
  });

  test('_reflect.deleteProperty should remove the designative `key` from target object', () => {
    const obj = {
      name: 'ddzy',
      age: 21,
    };
    const received = [
      'name',
      'skill',
    ];
    const expected = [
      true,
      true,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.deleteProperty(obj, v);
      expect(temp).toBe(expected[i]);
      expect(v in obj).toBeFalsy();
    }

    const temp = _reflect.deleteProperty(function () { }, 'name');
    expect(temp).toBeTruthy();
  });

  test('_reflect.getPrototypeOf should return the `__proto__` of the designative instance', () => {
    const obj = {};
    function Person1() { }
    const person = _reflect.construct(Person1, []);
    const str = '';
    const arr: any[] = [];
    const num = 0;
    const received = [
      obj,
      person,
      str,
      arr,
      num,
    ];
    const expected = [
      obj.__proto__,
      person.__proto__,
      str.__proto__,
      arr.__proto__,
      num.__proto__,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.getPrototypeOf(v);
      expect(temp).toBe(expected[i]);
    }
  });

  test('_reflect.setPrototypeOf should set the new prototype to the designative instance', () => {
    function Person1() { }
    Person1.prototype = {
      constructor: Person1,
      say() { },
    };
    const p1 = new Person1();
    const p2 = {
      run() { },
    };

    const received = [
      null,
      p2,
    ];
    const expected = [
      true,
      true,
    ];

    for (const [i, v] of received.entries()) {
      const temp = _reflect.setPrototypeOf(p1, v);
      expect(temp).toBe(expected[i]);
    }
  });
});
```
{% endcode %}



