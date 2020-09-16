# sort-draggable

### 说明

拖放排序组件

### 演示

{% embed url="https://codesandbox.io/s/businessdraggable-74zlf" %}

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/draggable/sort-draggable](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/draggable/sort-draggable)

### 配置

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">container</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x6302;&#x8F7D;&#x5230;&#x7684; DOM &#x5BB9;&#x5668;</td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">dataSource</td>
      <td style="text-align:left">
        <p>Array&lt;{</p>
        <p>titleText?: string; contentText?: string;</p>
        <p>}&gt;</p>
      </td>
      <td style="text-align:left">&#x6570;&#x636E;&#x6E90;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">animate</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x5F00;&#x542F;&#x62D6;&#x62FD;&#x52A8;&#x753B;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">dragWrapperStyle</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x62D6;&#x62FD;&#x5BB9;&#x5668;&#x7684;&#x6837;&#x5F0F;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">dragOriginStyle</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x62D6;&#x62FD;&#x5BF9;&#x8C61;&#x7684;&#x9ED8;&#x8BA4;&#x6837;&#x5F0F;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">dragOriginActiveStyle</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x62D6;&#x62FD;&#x5BF9;&#x8C61;&#x88AB;&#x62D6;&#x62FD;&#x65F6;&#x7684;&#x6837;&#x5F0F;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">dragTargetActiveStyle</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x4EA4;&#x6362;&#x76EE;&#x6807;&#x7684;&#x6D3B;&#x8DC3;&#x6837;&#x5F0F;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onDragStartHook</td>
      <td style="text-align:left">(origin: HTMLElement) =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onDragEnterHook</td>
      <td style="text-align:left">(origin: HTMLElement) =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onDragLeaveHook</td>
      <td style="text-align:left">(origin: HTMLElement) =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onDragOverHook</td>
      <td style="text-align:left">(origin: HTMLElement) =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onDropHook</td>
      <td style="text-align:left">(origin: HTMLElement) =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
  </tbody>
</table>

