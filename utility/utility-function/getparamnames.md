# getParamNames

### 说明

 获取函数的`形参`名称数组

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/getParamNames](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/function/getParamNames)

### 用法

{% code title="getParamNames.test.ts" %}
```typescript
import { getParamNames } from "../../utility/function/getParamNames";

describe('getParamNames', () => {
  test("getParamsNames should receive lots of parameters and return the array of each parameter's name.", () => {
    const received = [
      function (..._args: any[]) { },
      function func1(_name: string, _age: number) { },
      function func2(_name: string, _age: number, _address: string, ..._args: any[]) { },
    ];
    const expected = [
      [],
      ['_name', '_age'],
      ['_name', '_age', '_address'],
    ];

    for (const [i, v] of received.entries()) {
      const current = getParamNames(v);
      expect(current).toEqual(expected[i]);
    }
  });
});
```
{% endcode %}

