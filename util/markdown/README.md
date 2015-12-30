# A Markdown Editor

###预览

####多重选择格式化

####添加超级链接

####插入图片

###目前提供的功能

 * 标题、强调、斜体、插入代码、超链接、插入图片
 
 * 多行同时选择格式化

 * 插入控件错误基础检查

 * 插入图片动画u过渡

###不得不说的IE

首先，让我们一起fuck ie。基于ie9及其以下版本对FormData上传元素的不支持，a-markdown-editor的图片上传在ie9及以下不起作用。

最初，曾经使用iframe作为捕捉返回结果的方案，但是`document.write`在严格文档里是被禁止的，所以，索性排除掉ie9等版本的浏览器。

###依赖模块

 * [CodeMirror](https://github.com/tulayang/CodeMirror) 编辑代码高亮
 * [marked](https://github.com/chjj/marked)  html解析器
 * [highlight](https://github.com/isagalaev/highlight.js)  html代码高亮
 * [hogan](https://github.com/twitter/hogan.js) 前端模板引擎

###如何使用

在`index.html`中很好的标明了需要引入的css、js文件，以及如何调用AMD.make()构造器。


**导入css文件**

```js
<link type="text/css" rel="stylesheet" href="css/font-awesome/css/font-awesome.css"/>
<link type="text/css" rel="stylesheet" href="css/codemirror.css"/>
<link type="text/css" rel="stylesheet" href="css/highlight/xcode.css"/>
<link type="text/css" rel="stylesheet" href="css/amd.css"/>
<link type="text/css" rel="stylesheet" href="css/markdown.css"/>
```

**导入js文件**

```js
<script src="js/codemirror/lib/codemirror.js"></script>
<script src="js/codemirror/mode/markdown/markdown.js"></script>
<script src="js/amd.js"></script>
<script src="js/amd.hogan.js"></script>
<script src="js/amd.template.js"></script>
<script src="js/amd.marked.js"></script>
<script src="js/amd.highlight.js"></script>
<script src="js/amd.make.js"></script>
```

**调用构造器**

```js
AMD.make('#amd-editor', {
    amdBack: '/',
    amdPubMethod: 'post',
    amdPubAction: '/',
    amdSaveAction: '/',
    amdUploadImgAction: '/image',
    amdInitText: '',
    amdInitTitle: '',
    titleName: 'title',
    textName: 'text'
});
```

**服务器添加图片存储路由, 类似这样的程序**

```js
// 收到图片上传请求
// 保存图片
// 返回保存后图片的路径
```

###AMD.make构造器参数

 * amdUploadImgAction  上传图片的服务器路径
 * amdPubAction  发布按钮点击，文章内容提交的服务器路径
 * titleName  发布标题name值
 * textName  发布内容name值
