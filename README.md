## 文档在线预览编辑系统
---------------------------------------------------------------
之前做过在线编辑文档的功能，使用 [webdav](https://www.webdavsystem.com/) 来实现在线编辑，
存在的问题是编辑页面保存不可控（是否可以保存为版本、是否可以放弃保存等）。如果大家有实现类似功能，希望能提供帮助。

当前应用的主要功能是采用 openoffice 和 ckeditor 来实现文档的预览和编辑功能，先介绍操作步骤，再谈下面临的问题。

### 操作步骤
---------------------------------------------------------------

#### 文件列表
---------------------------------------------------------------
展示当前用户已上传的文件，并提供预览和删除操作

![列表页面](https://github.com/ekoz/kbase-doc/blob/master/src/main/resources/static/img/list.png?raw=true "列表页面")

#### 上传文件
---------------------------------------------------------------
上传文件时直接利用 openoffice 将文件转换成 html并保存

![上传页面](https://github.com/ekoz/kbase-doc/blob/master/src/main/resources/static/img/upload.png?raw=true "上传页面")

#### 预览文件
---------------------------------------------------------------
用户可以在预览界面单击编辑按钮，并实现保存或保存为版本功能

![预览页面](https://github.com/ekoz/kbase-doc/blob/master/src/main/resources/static/img/read.png?raw=true "预览页面")

![编辑页面](https://github.com/ekoz/kbase-doc/blob/master/src/main/resources/static/img/edit.png?raw=true "编辑页面")

### 已知问题
---------------------------------------------------------------
1. word中包含图片如何处理？目前是用Html正则将图片加上一个 地址 进行加载，这样在保存的时候，html文件的图片地址有异常
2. html 图片的正则未区分网络图片还是本地图片 
3. 用户修改word中的图片如何处理？
4. 将html转换成doc后，文件内容格式有误
5. windows 操作系统上如何删除一个正在被占用的进程？
6. 是否能很好的兼容 excel 和 ppt 的预览编辑功能 

### 感谢
---------------------------------------------------------------
[mirkonasato / jodconverter](https://github.com/mirkonasato/jodconverter)
[sbraconnier/jodconverter](https://github.com/sbraconnier/jodconverter)
