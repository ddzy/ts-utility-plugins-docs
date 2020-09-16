# invariant

### 说明

 自定义的异常处理机制\(`用于本仓库使用`\)

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/invariant](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/others/invariant)

### 用法

{% code title="invariant.test.ts" %}
```typescript
import { invariant } from "../../utility/others/invariant";

describe('invariant', () => {

  // ! Test successed
  // test('invariant should throw error when the condition to be true', () => {
  //   expect(utilityOthers.invariant(true, 'test error')).toThrowErrorMatchingSnapshot();
  // });

  test('invariant should not do anything when the condition to be false', () => {
    expect(invariant(false, 'test error')).toBeFalsy();
  });
});
```
{% endcode %}

