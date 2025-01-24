# typecho-sec
基于pache HTTP Server重写机制的typecho的若干安全规则
## 注意：本仓库中的规则集并不能保证你的个人网站的绝对安全。且启用规则可能会导致无法正常访问你的网站，请谨慎启用。

## 说明

#### 使用范围：
使用`Apache HTTP Server`和`typecho 1.2`搭建的个人论坛。
#### 原理
利用Apache的重写规则，将对于敏感文件外来访问请求进行重写。目前包含:  
1.将所有请求重写至index.php  
2.限制对var和usr文件夹下php文件的外网访问  
3.限制配置文件的访问  
4.限制对数据库文件的访问

## 使用教程
## 注意：在Typecho安装完成后才能启用本规则集，在更新组件时，请临时删除本规则集，以防止造成冲突。
根据Apache HTTP Server文档中对重写机制的说明，应当将本仓库中的`.htaccess`文件放在网站的根目录中。
#### 检查规则是否启用
使用浏览器访问[主机名]/[网站根目录下的文件路径]。如显示无法访问，则说明规则启用。


#### 参考
[Apache Rewrite 规则详解知识大全](https://www.cnblogs.com/zqw111/p/10919107.html)
[SQLite文件可直接被下载 typecho/typecho#1806](https://github.com/typecho/typecho/issues/1806)
[typecho 程序防黑客安全加固教程](https://www.80srz.com/posts/632.html)




