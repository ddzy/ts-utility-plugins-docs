# event-emitter

### 说明

模拟实现 `EventEmitter`

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/event-emitter](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/algorithm/event-emitter)

### 用法

{% code title="eventEmitter.test.ts" %}
```typescript
import { EventEmitter } from "../../utility/algorithm/event-emitter";

// ? EventEmitter
describe('EventEmitter tests', () => {
  test("EventEmitter.handleOn should put handlers into events and return the handler's own index", () => {
    const event = new EventEmitter({});
    const fun1 = function () {
      console.log('fun1');
    }
    const fun2 = function () {
      console.log('fun2');
    }
    const received = [
      {
        type: 'click',
        handler: fun1,
      },
      {
        type: 'click',
        handler: fun2,
      }
    ];
    const expected = [
      {
        type: 'click',
        index: 0,
      },
      {
        type: 'click',
        index: 1,
      }
    ];

    received.forEach(function (v, i) {
      const result = event.handleOn(v.type, v.handler);
      expect(result).toEqual(expected[i]);
    });
  });

  test('EventEmitter.handleRemove should remove the `dest handler` from events', () => {
    const event = new EventEmitter({});
    const fun1 = function () {
      console.log('fun1');
    }
    const fun2 = function () {
      console.log('fun2');
    }

    const r1 = event.handleOn('click', fun1);
    const r2 = event.handleOn('click', fun2);

    event.handleRemove(r2);

    let result: boolean = false;
    const events = event.events;
    events['click'].forEach(function (v, i) {
      if (i === r2.index) {
        if (!v) {
          result = true;
        }
      }
    });

    expect(result).toBeTruthy();
  });
});
```
{% endcode %}

### API

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">handleOn</td>
      <td style="text-align:left">
        <p>(type: string, handler: EventHandler) =&gt; {</p>
        <p>type: string, index: number</p>
        <p>}</p>
      </td>
      <td style="text-align:left">&#x653E;&#x7F6E;&#x4E8B;&#x4EF6;</td>
    </tr>
    <tr>
      <td style="text-align:left">handleEmit</td>
      <td style="text-align:left">(type: string) =&gt; EventEmitter</td>
      <td style="text-align:left">&#x53D1;&#x5C04;&#x4E8B;&#x4EF6;</td>
    </tr>
    <tr>
      <td style="text-align:left">handleRemove</td>
      <td style="text-align:left">(options: { type: string, index: number, },) =&gt; EventEmitter</td>
      <td
      style="text-align:left">&#x79FB;&#x9664;&#x67D0; <code>type</code> &#x7684;&#x67D0;&#x4E2A;<code>handler</code>
        </td>
    </tr>
  </tbody>
</table>

