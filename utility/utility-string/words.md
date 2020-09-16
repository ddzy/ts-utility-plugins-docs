# words

### 说明

 按照指定模式, 拆分字符串 `string` 中的词为数组

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/words](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/string/words)

### 用法

{% code title="words.test.ts" %}
```typescript
import { words } from "../../utility/string/words";

describe('Method words() test: ', () => {
  test('words() should use the default pattern while receive none pattern', () => {
    const received = {
      str: 'duan zhao _*$*$  y & ang a p     g',
      reg: /\W+/,
    };
    const expected = ["duan", "zhao _*$*$  y & ang a p     g"];

    const result = words(received.str, received.reg);

    result.forEach((v, i) => {
      expect(v).toBe(expected[i]);
    });
  });

  test('words() can use custom pattern', () => {
    const received = [
      {
        str: 'duan  zhao    yang',
        reg: /\s+/g,
      },
      {
        str: 'duan ### zhaoyang |%# s d h   dan',
        reg: /#+/g,
      },
    ];
    const expected = [
      ["duan", "zhao", "yang"],
      ["duan ", " zhaoyang ", "%", " s d h   dan"],
    ];

    received.forEach((outerV, outerI) => {
      const result = words(outerV.str, outerV.reg);

      result.forEach((innerV, innerI) => {
        expect(innerV).toBe(expected[outerI][innerI]);
      });
    });
  });
});
```
{% endcode %}

