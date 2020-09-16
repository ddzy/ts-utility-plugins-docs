# business-carousel

### 说明

纯原生轮播图插件, 包括渐变、滚动轮播, 以及其它的可配置项.

### 演示

{% embed url="https://codesandbox.io/s/businesscarousel-rmgbo" %}

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/carousel](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/carousel)

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
        <p>text: string, img: { url: string, target: string, },</p>
        <p>}&gt;</p>
      </td>
      <td style="text-align:left">&#x6570;&#x636E;&#x6E90;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">autoPlay</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x81EA;&#x52A8;&#x64AD;&#x653E;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">showDots</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x663E;&#x793A;&#x6307;&#x793A;&#x70B9;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">showArrows</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x663E;&#x793A;&#x7BAD;&#x5934;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">easing</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x8FC7;&#x6E21;&#x52A8;&#x753B;&#x66F2;&#x7EBF;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">effect</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x91C7;&#x7528;&#x4F55;&#x79CD;&#x8F6E;&#x64AD;(&quot;scroll&quot; |
        &quot;fade&quot;)</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">vertical</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x4E3A;&#x5782;&#x76F4;&#x65B9;&#x5411;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">duringTime</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x8FC7;&#x6E21;&#x52A8;&#x753B;&#x6301;&#x7EED;&#x65F6;&#x95F4;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">delayTime</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x8FC7;&#x6E21;&#x5EF6;&#x8FDF;&#x65F6;&#x95F4;</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">isHoverPause</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">&#x9F20;&#x6807;&#x60AC;&#x505C;&#x662F;&#x5426;&#x6682;&#x505C;&#x8F6E;&#x64AD;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">beforeChange</td>
      <td style="text-align:left">() =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">afterChange</td>
      <td style="text-align:left">() =&gt; void</td>
      <td style="text-align:left">*</td>
      <td style="text-align:left">false</td>
    </tr>
  </tbody>
</table>



