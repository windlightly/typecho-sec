# typecho-sec
基于Apache HTTP Server重写机制的typecho的若干安全规则 | 
Several security rules for Typecho based on the Apache HTTP Server rewrite mechanism
## 注意：本仓库中的规则集并不能保证你的个人网站的绝对安全。且启用规则可能会导致无法正常访问你的网站，请谨慎启用。

The rule sets in this repository do not guarantee absolute security for your personal website. Additionally, enabling these rules may result in the inability to access your website normally. Please enable them with caution.

## 说明
#### 背景
serv00的免费服务器的HTTP Server配置可能存在问题，使网站目录中的敏感文件可以直接通过输入URL进行下载：  
[NewApi .db 能直接下载](https://linux.do/t/topic/402126)  


#### 使用范围：
使用`Apache HTTP Server`和`typecho 1.2`搭建的个人论坛。  
#### 原理
利用Apache的重写规则，将对于敏感文件外来访问请求进行重写。目前包含:  
- 禁止目录索引
- 将所有请求重写至index.php
- 限制对var和usr文件夹的WEB访问
- 限制配置文件的访问
- 限制对数据库文件的访问.
- 其他

<br/>
<br/>

## 使用教程
## 注意：在Typecho安装完成后才能启用本规则集，在进行更新主程序、插件、主题等组件，直接操作数据库等关键动作时，请临时删除本规则集，以防止造成冲突。
<br/>
<br/>
  
- 启用规则：根据Apache HTTP Server文档中对重写机制的说明，将本仓库中的`.htaccess`文件放在网站的根目录中即可。
- 停用规则：删除`.htaccess`文件即可
  


#### 检查规则是否启用
使用浏览器访问[主机名]/[网站根目录下数据库文件或/usr,/var文件夹下php文件的文件路径]。如显示无法访问（例如404或503），则说明规则启用。

<br/>
<br/>

## 参考
[Apache Rewrite 规则详解知识大全](https://www.cnblogs.com/zqw111/p/10919107.html)  
[typecho/typecho#1806:SQLite文件可直接被下载](https://github.com/typecho/typecho/issues/1806)  
[typecho 程序防黑客安全加固教程](https://www.80srz.com/posts/632.html) 





