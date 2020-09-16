# dragger-upload

### 说明

拖拽上传插件

### 演示

{% embed url="https://codesandbox.io/s/businessupload-4z24x" %}



### 源码

[https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/upload/dragger-upload](https://github.com/ddzy/ts-utility-plugins/tree/master/src/ddzy/business/upload/dragger-upload)

### 配置

| Name | Type | Description | Required |
| :--- | :--- | :--- | :--- |
| container | string | 挂载到的 DOM 容器 | false |
| onChangeHook | \(e: Event\) =&gt; void | 文件发生改变时的钩子 | false |
| onBeforeUploadHook | \(file: File, fileList: File\[\]\) =&gt; boolean \| Promise | 上传到服务器前执行的钩子 | false |
| onUploadClickHook | \(file: File, FileList: File\[\]\) =&gt; boolean \| Promise | 上传至服务器按钮点击时的钩子 | false |
| onPreviewClickHook | \(file: File, fileList: File\[\]\) =&gt; void | 预览按钮点击时的钩子 | false |
| onRemoveClickHook | \(file: File, fileList: File\[\]\) =&gt; void | 从本地列表移除按钮点击时的钩子 | false |
| onUploadClickSuccessHook | \(file: File, fileList: File\[\]\) =&gt; void | 成功上传至服务器后的钩子 | false |
| onUploadClickFailHook | \(file: File, fileList: File\[\]\) =&gt; void | 上传至服务器失败时的钩子 | false |

### 总结

> 无法在ondrop内部直接使用`e.dataTransfer.files`获取文件列表

需要自定义数组, 再遍历一遍

> ondrag和onclick无法共存, 导致无法追加自定义样式

只需监听 onmouseup, 并在其中自行调用`label`标签的click方法 - `label.click()`

