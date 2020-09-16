# utility-array

### 说明

汇集有关`数组`的工具方法

### 源码

{% embed url="https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array" %}

### 目录

| Name | Description | Source | Docs |
| :--- | :--- | :--- | :--- |
| isStrictArray | 判断是否严格的数组 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/toStrictArray) | [文档](isstrictarray.md) |
| toFlatArrayOutPlace | 数组扁平化\(`非原地算法`\) | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/toFlatArrayOutPlace) | [文档](toflatarrayoutplace.md) |
| toStrictArray | 将给定的类数组转化为严格的数组\(`非原地`\) | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/toStrictArray) | [文档](tostrictarray.md) |
| trunk | 将源数组根据指定大小`分片` | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/trunk) | [文档](trunk.md) |
| compact | 过滤指定数组中的假值\(`0`、`''`、`false`、`null`、`undefined`、`NaN`\) | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/compact) | [文档](compact.md) |
| castArray | 将给定的值强制转成数组 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/castArray) | [文档](castarray.md) |
| \_concat | 将给定的任意数量的值追加至源数组 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/_concat) | [文档](_concat.md) |
| difference | 创建一个具有唯一`array`值的数组，每个值不包含在其他给定的数组中 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/difference) | [文档](difference.md) |
| drop | 创建一个切片数组, 去除`array`前面的`n`个元素 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/drop) | [文档](drop.md) |
| head | 获取数组的第一个元素 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/head) | [文档](head.md) |
| dropRight | 从源数组的右侧开始, 舍弃指定个数的值 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/dropRight) | [文档](dropright.md) |
| dropRightWhile | 创建一个切片数组, 去除源数组中从特定的`callback`返回假值开始到尾部的部分 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/dropRightWhile) | [文档](droprightwhile.md) |
| fill | 使用 `value` 值来填充（替换） `array`. 从 `start` 位置开始, 到 `end` 位置结束\(但不包含 `end` 位置\). | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/fill) | [文档](fill.md) |
| pullAll | 移除数组 `arr` 中所有和给定值相等的元素, 原地操作 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/pullAll) | [文档](pullall.md) |
| zip | 创建一个分组元素的数组, 数组的第一个元素包含所有给定数组的第一个元素, 数组的第二个元素包含所有给定数组的第二个元素, 以此类推. 打包后的数组的长度等于源二维数组的最大长度的项 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/zip) | [文档](zip.md) |
| \_join | 将数组中的所有元素转换为由 `separator` 分隔的字符串。 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/array/_join) | [文档](_join.md) |

