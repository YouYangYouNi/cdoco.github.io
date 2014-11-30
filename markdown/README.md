# A Markdown Editor

WYSIWYG

[DEMO] // 已下线

author: tulayang<br />
email: itulayangi@gmail.com iwangtongi@163.com

markdown的书写，比较起HTML是非常便利的，但并不是简单易行的。想要书写一套规则的文本，需要具备一定的markdown语法知识。**a markdown editor**希望提供部分的可控元素，在使用者熟悉语法之前，能够顺利的操作markdown文本。

*demo网站是托管在阿里云nodejs服务器，可使用容量很低，所以图片上传锁定了固定图片，无论你输入那个图片都是同一个图片。 [see DEMO]// 已下线*

###预览

####多重选择格式化
![screenshot](https://camo.githubusercontent.com/0f3332ab9848ec66cfcbd7a9f288bc701c805b36/687474703a2f2f64322e66726565702e636e2f3137305f3374625f313430363236303032333134657063393533333335342e706e67)
![screenshot](https://camo.githubusercontent.com/fd19d8e01a2ccb45997a215485db22848c2bc32d/687474703a2f2f64332e66726565702e636e2f3137305f3374625f313430363236303032333134646864653533333335342e706e67)

####添加超级链接

![screenshot](https://camo.githubusercontent.com/5ea859a310e823c0c2d5663426da102153e041f6/687474703a2f2f64332e66726565702e636e2f3137305f3374625f313430363236303032333134653033643533333335342e706e67)
![screenshot](https://camo.githubusercontent.com/2f97eba35cd23fb18dafcfc13a394fbe5d4c36a0/687474703a2f2f64332e66726565702e636e2f3137305f3374625f3134303632363030323331346c6b6a713533333335342e706e67)

####插入图片

![screenshot](https://camo.githubusercontent.com/28f9ace908323b2d1bfde7d93ab0ea4554848544/687474703a2f2f64332e66726565702e636e2f3137305f3374625f3134303632363030323331346b6779393533333335342e706e67)
![screenshot](https://camo.githubusercontent.com/9a5cf2a4b32fd32a3390920368411bff1581f583/687474703a2f2f64332e66726565702e636e2f3137305f3374625f313430363236303032333135616b79613533333335342e706e67)
![screenshot](https://camo.githubusercontent.com/4348fd0c23997bc80512573a8afc913811aca0dd/687474703a2f2f64332e66726565702e636e2f3137305f3374625f313430363236303032333134346230323533333335342e706e67)

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

到目前为止，**a markdown editor**的收尾做的有些仓促。未来还打算增加**mini版本的css**，编辑和预览放入一个控件位置以及增加前端图片格式预判断等。 
还未制作的完毕的部分：上传图片URL直接输入，未来更新。

*[see DEMO]// 已下线*
