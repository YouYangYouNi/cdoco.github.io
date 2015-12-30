###1.php.ini

----------

```
zend_extension = php/zend_ext/php_xdebug-2.2.5-5.5-vc11-x86_64.dll";

[xdebug]
xdebug.collect_params=1
xdebug.collect_return=1
xdebug.auto_trace=0
xdebug.trace_output_dir="/tmp"
xdebug.profiler_enable=0
xdebug.profiler_output_dir="/tmp" 
xdebug.max_nesting_level=100
xdebug.remote_enable=1
xdebug.remote_host=localhost
xdebug.remote_port=9003
```
ps：xdebug版本需要跟php对应，自己修改/tmp目录

###2.phpstorm

----------

1.设置debug端口为9003

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/1.png" alt="screenshot" />

2.设置servers域名，需要跟浏览器里访问你的项目的域名一致

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/2.png" alt="screenshot" />

3.设置IDE key，Host，Port

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/3.png" alt="screenshot" />

ps：IDE key填PhpStorm，Host 需要跟你上面填的域名一致，Port需要跟你php.ini里面的端口一致

###3.chrome

----------

1.安装Xdebug helper扩展，下载地址[xdebug-helper](http://www.mykurong.com/extensions/xdebughelper/)

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/4.png" alt="screenshot" />

2.点选项，设置IDE key，Domain filter

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/5.png" alt="screenshot" />

ps：IDE key 需要跟phpstorm里面设置的保持一致，Domain filter需要跟phpstorm里面设置的host域名保持一致

3.打开你的本地项目，如果你的项目域名跟刚刚配置的Domain filter一致 浏览器里会多一个xdebug的按钮。

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/6.png" alt="screenshot"/>

ps：默认是disable 需要选择debug

###配置完毕

ps：需要点开phpstorm里面的电话按钮，然后打断点刷新页面

<img width="" height="" class="amd-center" src="http://github.cdoco.com/images/xdebug/7.png" alt="screenshot" />
