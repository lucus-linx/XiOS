# 打开Mac自带的Apache

```shell
// 查看apache版本
$ sudo apachectl -v

// 启动apache
$ sudo apachectl start

// 重启apache
$ sudo apachectl restart
```



## 配置Apache

apache的主配置文件在路径/etc/apache2/下

修改httpd.conf 文件

- 备份原来的文件
    sudo cp /etc/apache2/httpd.conf /etc/apache2/httpd.conf.backup
- 修改主配置文件
    $vi /etc/apache2/httpd.conf



* 修改端口：

```
<IfDefine SERVER_APP_HAS_DEFAULT_PORTS>
    Listen 8080
</IfDefine>
<IfDefine !SERVER_APP_HAS_DEFAULT_PORTS>
    Listen 80
</IfDefine>
```



* 路径

```

#
# DocumentRoot: The directory out of which you will serve your
# documents. By default, all requests are taken from this directory, but
# symbolic links and aliases may be used to point to other locations.
#
DocumentRoot "/Library/WebServer/Documents"
<Directory "/Library/WebServer/Documents">
    #
    # Possible values for the Options directive are "None", "All",
    # or any combination of:
    #   Indexes Includes FollowSymLinks SymLinksifOwnerMatch ExecCGI MultiViews
    #
    # Note that "MultiViews" must be named *explicitly* --- "Options All"
    # doesn't give it to you.
    #
    # The Options directive is both complicated and important.  Please see
    # http://httpd.apache.org/docs/2.4/mod/core.html#options
    # for more information.
    #
    Options FollowSymLinks Multiviews
    MultiviewsMatch Any

    #
    # AllowOverride controls what directives may be placed in .htaccess files.
    # It can be "All", "None", or any combination of the keywords:
    #   AllowOverride FileInfo AuthConfig Limit
    #
    AllowOverride None

    #
    # Controls who can get stuff from this server.
    #
    Require all granted
</Directory>
```





```json
//在文件里加入,前面的例子可以用＃ 注释掉
<VirtualHost *:80>
DocumentRoot "项目文档根目录"
ServerName 服务器名称
ErrorLog "/private/var/log/apache2/mysites-error_log"
CustomLog "/private/var/log/apache2/mysites-access_log" common
<Directory "项目文档根目录">
Options FollowSymLinks Multiviews Indexes
MultiviewsMatch Any
AllowOverride None
Require all granted
</Directory>
<Proxy *>
Order deny,allow
Allow from all
</Proxy>
// 配置请求转发服务器 和 环境路径(反向代理)
ProxyPass /web http://example.com/web
ProxyPassReverse /web http://example.com/web
</VirtualHost>
```

