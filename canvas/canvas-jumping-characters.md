# canvas-jumping-characters

### 说明

跳动的字符插件, 鼠标点击时, 会产生文字并逐渐消失的效果, 同样可以用作博客组件, 增强观赏性.

### 演示

{% embed url="https://codesandbox.io/s/canvasjumpingcharacters-wckpv" %}

### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/canvas/jumping-characters](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/canvas/jumping-characters)

### 配置

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| container | string | 挂载到的 DOM 容器 | true |
| cvsWidth | number | 画布的宽 | false |
| cvsHeight | number | 画布的高 | false |
| cvsBgColor | string | 画布的背景颜色 | false |
| text | string\[\] | 文字数组 | false |
| textColor | string\[\] | 文字颜色数组 | false |
| textSize | number | 文字大小 | false |
| safeDistance | number | 安全距离后文字消失 | false |
| initialOpacity | number | 文字初始透明度 | false |
| speed | number | 文字移动速度 | false |



