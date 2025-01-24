# typecho-sec
基于pache HTTP Server重写机制的typecho的若干安全规则


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
根据Apache HTTP Server文档中对重写机制的说明，应当将本仓库中的`.htaccess`文件放在网站的根目录中。
#### 检查规则是否启用
使用浏览器访问[主机名]/[网站根目录下的文件路径]。如显示无法访问，则说明规则启用。



