# business-tabs

### 说明

选项卡切换组件

### 演示

{% embed url="https://codesandbox.io/s/businesstab-u5z9j" %}

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/tabs](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/tabs)

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
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">dataSource</td>
      <td style="text-align:left">
        <p>Array&lt;{</p>
        <p>tabPaneTitle: { icon?: string, text?: string, }, tabPaneContent: { text?:
          string, },</p>
        <p>}&gt;</p>
      </td>
      <td style="text-align:left">&#x6570;&#x636E;&#x6E90;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">&apos;line&apos; | &apos;card&apos;</td>
      <td style="text-align:left">&#x9009;&#x9879;&#x5361;&#x7C7B;&#x578B;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">mouse</td>
      <td style="text-align:left">&apos;mouseenter&apos; | &apos;click&apos;</td>
      <td style="text-align:left">&#x9F20;&#x6807;&#x5207;&#x6362;&#x65B9;&#x5F0F;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">defaultActiveKey</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x9ED8;&#x8BA4;&#x663E;&#x793A;&#x7684;&#x9009;&#x9879;&#x5361;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">tabBarGap</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x9009;&#x9879;&#x5361;&#x95F4;&#x8DDD;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">tabBarStyle</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x9009;&#x9879;&#x5361;&#x6807;&#x9898;&#x7684;&#x6837;&#x5F0F;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">tabBarLineStyle</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x9009;&#x9879;&#x5361;&#x6807;&#x9898;&#x7EBF;&#x7684;&#x6837;&#x5F0F;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">animated</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x5F00;&#x542F;&#x8FC7;&#x6E21;&#x52A8;&#x753B;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onChange</td>
      <td style="text-align:left">(activeKey: number | string) =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">onTabClick</td>
      <td style="text-align:left">() =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
  </tbody>
</table>



