# utility-object

### 说明

汇集有关`对象`的工具方法

### 源码

{% embed url="https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object" %}

### 目录

| Name | Description | Source | Docs |
| :--- | :--- | :--- | :--- |
| isPlainObject | 判断是否普通的`键值对`对象 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/isPlainObject) | [文档](isplainobject.md) |
| get | 根据`object`对象的`path`路径获取值 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/get) | [文档](get.md) |
| forIn | 使用 `iteratee` 遍历对象的自身和继承的可枚举属性. `iteratee` 会传入3个参数: \(value, key, object\). 如果返回 `false`, iteratee 会提前退出遍历. | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/forIn) | [文档](forin.md) |
| forOwn | 遍历对象自身的可枚举属性, 不包括继承而来的属性 | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/forOwn) | [文档](forown.md) |
| create | 模拟实现 `Object.create()` | [源码](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/utility/object/create) | [文档](create.md) |



