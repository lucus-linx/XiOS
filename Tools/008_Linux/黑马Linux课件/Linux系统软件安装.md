# 实战章节：在Linux上部署各类软件

# 前言

## 为什么学习各类软件在Linux上的部署

在前面，我们学习了许多的Linux命令和高级技巧，这些知识点比较零散，同学们跟随着课程的内容进行练习虽然可以基础掌握这些命令和技巧的使用，但是并没有一些具体的实操能够串联起来这些知识点。

所以，现在我们设计了各类软件在Linux上部署安装的实战章节，可以让同学们：

- 对前面学习的各类操作命令进行复习和练习，从而深度掌握它们
- 本章节中演示部署的软件，包含了IT行业各类岗位中所必须使用的，如：Java后台、大数据开发、运维开发、测试、AI等。无论学习Linux后从事什么岗位，这些内容都会给你带来帮助

> 对于零基础学员，实战课程中所讲解的软件大概率多数大家并不了解。
>
> 所以，课程仅涉及到安装部署，不对软件的使用做详细说明。
>
> 同学们在这个过程中，可能会遇到各种各样的错误，`不要怕`，解决它，将会给你带来极大的提升。

### 学习目标

对于本部分的内容学习，我们设计两个目标：

- 对于零基础或未从业的学员，不要求深入理解所安装部署的软件是什么，仅仅能够跟随课程成功的将其部署安装并运行成功即可

  在这个过程中，主要锻炼大家对Linux操作系统的熟练度，此乃零基础未从业学员的第一学习目标

- 对于有基础或已从业的学员，本章节讲解的软件涵盖了大多数IT从业者所能接触到的，特别是大数据开发、后端开发两个主流方向，可以作为参考资料，以便在工作中有所帮助。



本章节内的各类软件安装，==不强制要求全部学习==

1. 零基础学员，建议全部学习，作为前面学习内容的总结和实战
2. IT从业者、有经验学员，可以按需选择，选择工作中需要用到的进行学习



> 章节内包含的软件并非100%涵盖了IT开发领域中所需要的内容。
>
> 如果您对某些软件的安装有强烈需求，且课程中没有提供教程，可以私信B站："黑马大数据曹老师"，老师会酌情根据时间安排补充上去哦。



## 为什么不使用PPT而是使用文档进行授课

从现在开始，将要进入到Linux的实操阶段，在这个阶段我们将会涉及到非常多的软件部署等操作，涉及到：

- 各类命令的使用
- 各种过程的结果
- 复杂的流程步骤
- 等

这些信息的展示，并不适合于使用PPT作为载体进行授课，所以从现在开始我们将使用操作文档的模式为大家进行讲解。



> 使用文档模式还有一个好处，除了学习视频以外，拿到课程中使用的操作文档，同样可以作为重要的参考手册进行使用。
>
> 一举两得

## 前置要求

1. 实战章节要求同学们==务必全部学习前面的知识点==，即：初识Linux、Linux基础命令、Linux权限管理、Linux高阶技巧这4个章节，请勿跳过前面的章节学习实战章节。
2. 实战章节中会开启多台虚拟机，请尽量确保电脑的内存在：8GB（包含8GB）以上。如内存不足可以扩充内存条或购买阿里云、UCloud等云服务器临时使用（1个月多台低配服务器几十块左右）

> 对于云平台上购买服务器，可以参阅最后的章节（云服务）



## 注意

下面全部的软件安装的相关流程，90%都是取自软件自身的官方网站。

一个合格的程序员要有良好的信息收集能力哦





# MySQL数据库管理系统安装部署【简单】

## 简介

MySQL数据库管理系统（后续简称MySQL），是一款知名的数据库系统，其特点是：轻量、简单、功能丰富。

MySQL数据库可谓是软件行业的明星产品，无论是后端开发、大数据、AI、运维、测试等各类岗位，基本上都会和MySQL打交道。



让我们从MySQL开始，进行实战的Linux软件安装部署。

本次课程分为2个版本进行安装：

- MySQL 5.7版本安装
- MySQL 8.x版本安装

> 由于MySQL5.x和8.x各自有许多使用者，所以这两个版本我们都演示安装一遍





## 注意

MySQL的安装过程中，除了会使用Linux命令外，还会使用到少量的数据库专用的：SQL语句

对于SQL语句我们并未涉及，所以可以跟随教程的内容，复制粘贴即可



如对MySQL感兴趣，可以学习BiliBili黑马程序员视频：[2022新版黑马程序员MySQL知识精讲+mysql实战案例_零基础mysql数据库入门到高级全套教程](https://www.bilibili.com/video/BV1iF411z7Pu)

> 如有时间，建议可以在学习完Linux系统之后，学习一下MySQL数据库
>
> 无论从事什么方面的开发，Java后端、大数据、AI、前端、Linux运维等，都会要求掌握MySQL数据库的
>
> 可以说，MySQL是IT开发从业者必备的技能了。



## MySQL5.7版本在CentOS系统安装

> 注意：安装操作需要root权限



MySQL的安装我们可以通过前面学习的yum命令进行。



### 安装

1. 配置yum仓库

   ```shell
   # 更新密钥
   rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022
   
   # 安装Mysql yum库
   rpm -Uvh http://repo.mysql.com//mysql57-community-release-el7-7.noarch.rpm
   ```

   ![image-20221012182514865](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012182514.png)

   > 由于MySQL并不在CentOS的官方仓库中，所以我们通过上述rpm命令：
   >
   > - 导入MySQL仓库的密钥
   > - 配置MySQLQ的yum仓库

2. 使用yum安装MySQL

   ```shell
   # yum安装Mysql
   yum -y install mysql-community-server
   ```

   ![image-20221012182555420](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012182556.png)

3. 安装完成后，启动MySQL并配置开机自启动

   ```shell
   systemctl start mysqld		# 启动
   systemctl enable mysqld		# 开机自启
   ```

   > MySQL安装完成后，会自动配置为名称叫做：`mysqld`的服务，可以被systemctl所管理

4. 检查MySQL的运行状态

   ```shell
   systemctl status mysqld
   ```

   ![image-20221012182716598](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012182716.png)



### 配置

主要配置管理员用户root的密码以及配置允许远程登录的权限。



1. 获取MySQL的初始密码

   ```shell
   # 通过grep命令，在/var/log/mysqld.log文件中，过滤temporary password关键字，得到初始密码
   grep 'temporary password' /var/log/mysqld.log
   ```

   ![image-20221012182744115](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012182744.png)

2. 登陆MySQL数据库系统

   ```shell
   # 执行
   mysql -uroot -p
   # 解释
   # -u，登陆的用户，MySQL数据库的管理员用户同Linux一样，是root
   # -p，表示使用密码登陆
   
   # 执行完毕后输入刚刚得到的初始密码，即可进入MySQL数据库
   ```

   ![image-20221012182805966](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012182806.png)

3. 修改root用户密码

   ```sql
   # 在MySQL控制台内执行
   ALTER USER 'root'@'localhost' IDENTIFIED BY '密码';	-- 密码需要符合：大于8位，有大写字母，有特殊符号，不能是连续的简单语句如123，abc
   ```

4. [扩展]，配置root的简单密码

   > 我们可以给root设置简单密码，如123456.
   >
   > 请注意，此配置仅仅是用于测试环境或学习环境的MySQL，如果是正式使用，请勿设置简单密码

   ```sql
   # 如果你想设置简单密码，需要降低Mysql的密码安全级别
   set global validate_password_policy=LOW; # 密码安全级别低
   set global validate_password_length=4;	 # 密码长度最低4位即可
   
   # 然后就可以用简单密码了（课程中使用简单密码，为了方便，生产中不要这样）
   ALTER USER 'root'@'localhost' IDENTIFIED BY '简单密码';
   ```

5. [扩展]，配置root运行远程登录

   > 默认情况下，root用户是不运行远程登录的，只允许在MySQL所在的Linux服务器登陆MySQL系统
   >
   > 请注意，允许root远程登录会带来安全风险

   ```sql
   # 授权root远程登录
   grant all privileges on *.* to root@"IP地址" identified by '密码' with grant option;  
   # IP地址即允许登陆的IP地址，也可以填写%，表示允许任何地址
   # 密码表示给远程登录独立设置密码，和本地登陆的密码可以不同
   
   # 刷新权限，生效
   flush privileges;
   ```

6. 退出MySQL控制台页面

   ```sql
   # 退出命令
   exit
   
   # 或者通过快捷键退出：ctrl + d
   ```

7. 检查端口

   MySQL默认绑定了3306端口，可以通过端口占用检查MySQL的网络状态

   ```shell
   netstat -anp | grep 3306
   ```

   ![image-20221012183746802](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012183746.png)



至此，MySQL就安装完成并可用了，请妥善保存好MySQL的root密码。





## MySQL8.0版本在CentOS系统安装

> 注意：安装操作需要root权限



### 安装



1. 配置yum仓库

   ```shell
   # 更新密钥
   rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022
   
   # 安装Mysql8.x版本 yum库
   rpm -Uvh https://dev.mysql.com/get/mysql80-community-release-el7-2.noarch.rpm
   ```

2. 使用yum安装MySQL

   ```shell
   # yum安装Mysql
   yum -y install mysql-community-server
   ```

3. 安装完成后，启动MySQL并配置开机自启动

   ```shell
   systemctl start mysqld		# 启动
   systemctl enable mysqld		# 开机自启
   ```

   > MySQL安装完成后，会自动配置为名称叫做：`mysqld`的服务，可以被systemctl所管理

4. 检查MySQL的运行状态

   ```shell
   systemctl status mysqld
   ```



### 配置

主要修改root密码和允许root远程登录



1. 获取MySQL的初始密码

   ```shell
   # 通过grep命令，在/var/log/mysqld.log文件中，过滤temporary password关键字，得到初始密码
   grep 'temporary password' /var/log/mysqld.log
   ```

2. 登录MySQL数据库系统

   ```shell
   # 执行
   mysql -uroot -p
   # 解释
   # -u，登陆的用户，MySQL数据库的管理员用户同Linux一样，是root
   # -p，表示使用密码登陆
   
   # 执行完毕后输入刚刚得到的初始密码，即可进入MySQL数据库
   ```

3. 修改root密码

   ```sql
   ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '密码';	-- 密码需要符合：大于8位，有大写字母，有特殊符号，不能是连续的简单语句如123，abc
   ```

4. [扩展]，配置root的简单密码

   > 我们可以给root设置简单密码，如123456.
   >
   > 请注意，此配置仅仅是用于测试环境或学习环境的MySQL，如果是正式使用，请勿设置简单密码

   ```sql
   set global validate_password.policy=0;		# 密码安全级别低
   set global validate_password.length=4;		# 密码长度最低4位即可
   ```

   

5. 允许root远程登录，并设置远程登录密码

   > 默认情况下，root用户是不运行远程登录的，只允许在MySQL所在的Linux服务器登陆MySQL系统
   >
   > 请注意，允许root远程登录会带来安全风险

   ```sql
   # 第一次设置root远程登录，并配置远程密码使用如下SQL命令
   create user 'root'@'%' IDENTIFIED WITH mysql_native_password BY '密码!';	-- 密码需要符合：大于8位，有大写字母，有特殊符号，不能是连续的简单语句如123，abc
   
   # 后续修改密码使用如下SQL命令
   ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '密码';
   ```

6. 退出MySQL控制台页面

   ```sql
   # 退出命令
   exit
   
   # 或者通过快捷键退出：ctrl + d
   ```

7. 检查端口

   MySQL默认绑定了3306端口，可以通过端口占用检查MySQL的网络状态

   ```shell
   netstat -anp | grep 3306
   ```

   ![image-20221012192303607](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/12/20221012192303.png)





至此，MySQL就安装完成并可用了，请妥善保存好MySQL的root密码。





## MySQL5.7版本在Ubuntu（WSL环境）系统安装

> 课程中配置的WSL环境是最新的Ubuntu22.04版本，这个版本的软件商店内置的MySQL是8.0版本
>
> 所以我们需要额外的步骤才可以安装5.7版本的MySQL



安装操作需root权限，你可以：

1. 通过 sudo su -，切换到root用户

   > 课程中选择这种方式操作

2. 或在每一个命令前，加上sudo，用来临时提升权限





### 安装

1. 下载apt仓库文件

   ```shell
   # 下载apt仓库的安装包，Ubuntu的安装包是.deb文件
   wget https://dev.mysql.com/get/mysql-apt-config_0.8.12-1_all.deb
   ```

   ![image-20221016094103315](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094103.png)

2. 配置apt仓库

   ```shell
   # 使用dpkg命令安装仓库
   dpkg -i mysql-apt-config_0.8.12-1_all.deb
   ```

   弹出框中选择：`ubuntu bionic` （Ubuntu18.04系统的代号是bionic，选择18.04的版本库用来安装）

   ![image-20221016094142343](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094142.png)

   弹出框中选择：`MySQL Server & Cluster`

   ![image-20221016094216377](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094216.png)

   弹出框中选择：`mysql-5.7`

   ![image-20221016094254397](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094254.png)

   最后选择：`ok`

   ![image-20221016094306917](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094306.png)

3. 更新apt仓库的信息

   ```shell
   # 首先导入仓库的密钥信息
   apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 467B942D3A79BD29
   # 更新仓库信息
   apt update
   ```

4. 检查是否成功配置MySQL5.7的仓库

   ```shell
   apt-cache policy mysql-server
   ```

   ![image-20221016094546943](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094546.png)

   看到如图所示字样，即成功

5. 安装MySQL5.7

   ```shell
   # 使用apt安装mysql客户端和mysql服务端
   apt install -f -y mysql-client=5.7* mysql-community-server=5.7*
   ```

   弹出框中输入root密码并选择ok，密码任意，课程中以123456代替

   ![image-20221016094941439](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094941.png)

   再次输入root密码确认

   ![image-20221016094954505](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016094954.png)

6. 启动MySQL

   ```shell
   /etc/init.d/mysql start			# 启动
   /etc/init.d/mysql stop			# 停止
   /etc/init.d/mysql status		# 查看状态
   ```

   ![image-20221016095259172](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095259.png)

7. 对MySQL进行初始化

   ```shell
   # 执行如下命令，此命令是MySQL安装后自带的配置程序
   mysql_secure_installation
   # 可以通过which命令查看到这个自带程序所在的位置
   root@DESKTOP-Q89USRE:~# which mysql_secure_installation
   /usr/bin/mysql_secure_installation
   ```

   1. 输入密码：

      ![image-20221016095458755](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095458.png)

   2. 是否开启密码验证插件，如果需要增强密码安全性，输入`y`并回车，不需要直接回车（课程中选择直接回车）

      ![image-20221016095537716](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095537.png)

   3. 是否更改root密码，需要输入`y`回车，不需要直接回车（课程不更改）

      ![image-20221016095621386](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095621.png)

   4. 是否移除匿名用户，移除输入`y`回车，不移除直接回车（课程选择移除）

      ![image-20221016101232827](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101232.png)

   5. 是否进制root用户远程登录，禁止输入`y`回车，不禁止直接回车（课程选择不禁止）

      ![image-20221016101324577](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101324.png)

   6. 是否移除自带的测试数据库，移除输入`y`回车，不移除直接回车（课程选择不移除）

      ![image-20221016101404392](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101404.png)

   7. 是否刷新权限，刷新输入`y`回车，不刷新直接回车（课程选择刷新）

      ![image-20221016101442459](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101442.png)

8. 登陆MySQL

   ```shell
   mysql -uroot -p
   # 输入密码即可登陆成功
   ```

   ![image-20221016101524498](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101524.png)



至此，在Ubuntu上安装MySQL5.7版本成功。





## MySQL8.0版本在Ubuntu（WSL环境）系统安装

> 课程中配置的WSL环境是最新的Ubuntu22.04版本，这个版本的软件商店内置的MySQL是8.0版本
>
> 所以直接可以通过apt安装即可

> 注意，课程是以WSL获得的Ubuntu操作系统环境。
>
> 如果你通过VMware虚拟机的方式获得了Ubuntu操作系统环境，操作步骤不用担心，和课程中使用WSL环境是==完全一致的==



安装操作需root权限，你可以：

1. 通过 sudo su -，切换到root用户

   > 课程中选择这种方式操作

2. 或在每一个命令前，加上sudo，用来临时提升权限



### 安装

1. 如果已经安装过MySQL5.7版本，需要卸载仓库信息哦

   ```shell
   # 卸载MySQL5.7版本
   apt remove -y mysql-client=5.7* mysql-community-server=5.7*
   
   # 卸载5.7的仓库信息
   dpkg -l | grep mysql | awk '{print $2}' | xargs dpkg -P
   ```

2. 更新apt仓库信息

   ```shell
   apt update
   ```

3. 安装mysql

   ```shell
   apt install -y mysql-server
   ```

4. 启动MySQL

   ```shell
   /etc/init.d/mysql start			# 启动
   /etc/init.d/mysql stop			# 停止
   /etc/init.d/mysql status		# 查看状态
   ```

5. 登陆MySQL设置密码

   ```shell
   # 直接执行：mysql
   mysql
   ```

6. 设置密码

   ```sql
   ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
   ```

7. 退出MySQL控制台

   ```shell
   exit
   ```

8. 对MySQL进行初始化

   ```shell
   # 执行如下命令，此命令是MySQL安装后自带的配置程序
   mysql_secure_installation
   # 可以通过which命令查看到这个自带程序所在的位置
   root@DESKTOP-Q89USRE:~# which mysql_secure_installation
   /usr/bin/mysql_secure_installation
   ```

   1. 输入密码：

      ![image-20221016095458755](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095458.png)

   2. 是否开启密码验证插件，如果需要增强密码安全性，输入`y`并回车，不需要直接回车（课程中选择直接回车）

      ![image-20221016095537716](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095537.png)

   3. 是否更改root密码，需要输入`y`回车，不需要直接回车（课程不更改）

      ![image-20221016095621386](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016095621.png)

   4. 是否移除匿名用户，移除输入`y`回车，不移除直接回车（课程选择移除）

      ![image-20221016101232827](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101232.png)

   5. 是否进制root用户远程登录，禁止输入`y`回车，不禁止直接回车（课程选择不禁止）

      ![image-20221016101324577](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101324.png)

   6. 是否移除自带的测试数据库，移除输入`y`回车，不移除直接回车（课程选择不移除）

      ![image-20221016101404392](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101404.png)

   7. 是否刷新权限，刷新输入`y`回车，不刷新直接回车（课程选择刷新）

      ![image-20221016101442459](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016101442.png)

9. 重新登陆MySQL（用更改后的密码）

   ```shell
   mysql -uroot -p
   ```

   ![image-20221016110414182](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/16/20221016110414.png)

   



至此，在Ubuntu上安装MySQL5.7版本成功。



# Tomcat安装部署【简单】

## 简介

Tomcat 是由 Apache 开发的一个 Servlet 容器，实现了对 Servlet 和 JSP 的支持，并提供了作为Web服务器的一些特有功能，如Tomcat管理和控制平台、安全域管理和Tomcat阀等。



简单来说，Tomcat是一个WEB应用程序的托管平台，可以让用户编写的WEB应用程序，被Tomcat所托管，并提供网站服务。

> 即让用户开发的WEB应用程序，变成可以被访问的网页。



## 安装

Tomcat的安装非常简单，主要分为2部分：

1. 安装JDK环境
2. 解压并安装Tomcat



> 本次安装使用Tomcat版本是：10.0.27版本，需要Java（JDK）版本最低为JDK8或更高版本
>
> 课程中使用的JDK版本是：JDK8u351版本



### 安装JDK环境

1. 下载JDK软件

   https://www.oracle.com/java/technologies/downloads

   在页面下方找到：

   <img src="https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/17/20221017163411.png" alt="image-20221017163411651" style="zoom: 67%;" />

   下载`jdk-8u351-linux-x64.tar.gz`

   ![image-20221017163440491](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/17/20221017163440.png)

   ==在弹出的页面中输入Oracle的账户密码即可下载（如无账户，请自行注册，注册是免费的）==

2. 登陆Linux系统，切换到root用户

   ![](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/17/20221017163607.png)

3. 通过FinalShell，上传下载好的JDK安装包

   ![image-20221017163706026](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/17/20221017163706.png)

4. 创建文件夹，用来部署JDK，将JDK和Tomcat都安装部署到：/export/server 内

   ```shell
   mkdir -p /export/server
   ```

5. 解压缩JDK安装文件

   ```shell
   tar -zxvf jdk-8u351-linux-x64.tar.gz -C /export/server
   ```

6. 配置JDK的软链接

   ```shell
   ln -s /export/server/jdk1.8.0_351 /export/server/jdk
   ```

7. 配置JAVA_HOME环境变量，以及将$JAVA_HOME/bin文件夹加入PATH环境变量中

   ```shell
   # 编辑/etc/profile文件
   export JAVA_HOME=/export/server/jdk
   export PATH=$PATH:$JAVA_HOME/bin
   ```

8. 生效环境变量

   ```shell
   source /etc/profile
   ```

9. 配置java执行程序的软链接

   ```shell
   # 删除系统自带的java程序
   rm -f /usr/bin/java
   # 软链接我们自己安装的java程序
   ln -s /export/server/jdk/bin/java /usr/bin/java
   ```

10. 执行验证：

    ```shell
    java -version
    javac -version
    ```



### 解压并部署Tomcat

> Tomcat建议使用非Root用户安装并启动
>
> 可以创建一个用户：tomcat用以部署



1. 首先，放行tomcat需要使用的8080端口的外部访问权限

   > CentOS系统默认开启了防火墙，阻止外部网络流量访问系统内部
   >
   > 所以，如果想要Tomcat可以正常使用，需要对Tomcat默认使用的8080端口进行放行
   >
   > 放行有2种操作方式：
   >
   > 1. 关闭防火墙
   > 2. 配置防火墙规则，放行端口

   ```shell
   # 以下操作2选一即可
   # 方式1：关闭防火墙
   systemctl stop firewalld		# 关闭防火墙
   systemctl disable firewalld		# 停止防火墙开机自启
   
   # 方式2：放行8080端口的外部访问
   firewall-cmd --add-port=8080/tcp --permanent		# --add-port=8080/tcp表示放行8080端口的tcp访问，--permanent表示永久生效
   firewall-cmd --reload								# 重新载入防火墙规则使其生效
   ```

   > 方便起见，建议同学们选择方式1，直接关闭防火墙一劳永逸
   >
   > 防火墙的配置非常复杂，后面会视情况独立出一集防火墙配置规则的章节。

2. 以root用户操作，创建tomcat用户

   ```shell
   # 使用root用户操作
   useradd tomcat
   # 可选，为tomcat用户配置密码
   passwd tomcat
   ```

3. 下载Tomcat安装包

   ```shell
   # 使用root用户操作
   wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.27/bin/apache-tomcat-10.0.27.tar.gz
   # 如果出现https相关错误，可以使用--no-check-certificate选项
   wget --no-check-certificate https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.27/bin/apache-tomcat-10.0.27.tar.gz
   ```

   > 如果Linux内下载过慢，可以复制下载链接在Windows系统中使用迅雷等软件加速下载然后上传到Linux内即可
   >
   > 或者使用课程资料中提供的安装包

4. 解压Tomcat安装包

   ```shell
   # 使用root用户操作，否则无权限解压到/export/server内，除非修改此文件夹权限
   tar -zxvf apache-tomcat-10.0.27.tar.gz -C /export/server
   ```

5. 创建Tomcat软链接

   ```shell
   # 使用root用户操作
   ln -s /export/server/apache-tomcat-10.0.27 /export/server/tomcat
   ```

6. 修改tomcat安装目录权限

   ```shell
   # 使用root用户操作，同时对软链接和tomcat安装文件夹进行修改，使用通配符*进行匹配
   chown -R tomcat:tomcat /export/server/*tomcat*
   ```

7. 切换到tomcat用户

   ```shell
   su - tomcat
   ```

8. 启动tomcat

   ```shell
   /export/server/tomcat/bin/startup.sh
   ```

9. tomcat启动在8080端口，可以检查是否正常启动成功

   ```shell
   netstat -anp | grep 8080
   ```

   ![image-20221017223814737](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/17/20221017223814.png)

10. 打开浏览器，输入：

    http://centos:8080或http://192.168.88.130:8080

    使用主机名（需配置好本地的主机名映射）或IP地址访问Tomcat的WEB页面

    ![image-20221017223915498](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/17/20221017223915.png)



至此，Tomcat安装配置完成。





# Nginx安装部署【简单】

## 简介

*Nginx* (engine x) 是一个高性能的HTTP和反向代理web服务器，同时也提供了IMAP/POP3/SMTP服务。

同Tomcat一样，Nginx可以托管用户编写的WEB应用程序成为可访问的网页服务，同时也可以作为流量代理服务器，控制流量的中转。



Nginx在WEB开发领域，基本上也是必备组件之一了。



## 安装

Nginx同样需要配置额外的yum仓库，才可以使用yum安装

> 安装Nginx的操作需要root身份



1. 安装yum依赖程序

   ```shell
   # root执行
   yum install -y yum-utils
   ```

2. 手动添加，nginx的yum仓库

   yum程序使用的仓库配置文件，存放在：`/etc/yum.repo.d`内。

   ```shell
   # root执行
   # 创建文件使用vim编辑
   vim /etc/yum.repos.d/nginx.repo
   # 填入如下内容并保存退出
   [nginx-stable]
   name=nginx stable repo
   baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
   gpgcheck=1
   enabled=1
   gpgkey=https://nginx.org/keys/nginx_signing.key
   module_hotfixes=true
   
   [nginx-mainline]
   name=nginx mainline repo
   baseurl=http://nginx.org/packages/mainline/centos/$releasever/$basearch/
   gpgcheck=1
   enabled=0
   gpgkey=https://nginx.org/keys/nginx_signing.key
   module_hotfixes=true
   ```

   > 通过如上操作，我们手动添加了nginx的yum仓库

3. 通过yum安装最新稳定版的nginx

   ```shell
   # root执行
   yum install -y nginx
   ```

4. 启动

   ```shell
   # nginx自动注册了systemctl系统服务
   systemctl start nginx		# 启动
   systemctl stop nginx		# 停止
   systemctl status nginx		# 运行状态
   systemctl enable nginx		# 开机自启
   systemctl disable nginx		# 关闭开机自启
   ```

5. 配置防火墙放行

   nginx默认绑定80端口，需要关闭防火墙或放行80端口

   ```shell
   # 方式1（推荐），关闭防火墙
   systemctl stop firewalld		# 关闭
   systemctl disable firewalld		# 关闭开机自启
   
   # 方式2，放行80端口
   firewall-cmd --add-port=80/tcp --permanent		# 放行tcp规则下的80端口，永久生效
   firewall-cmd --reload							# 重新加载防火墙规则
   ```

6. 启动后浏览器输入Linux服务器的IP地址或主机名即可访问

   http://192.168.88.130 或 http://centos

   > ps：80端口是访问网站的默认端口，所以后面无需跟随端口号
   >
   > 显示的指定端口也是可以的比如：
   >
   > - http://192.168.88.130:80
   > - http://centos:80



至此，Nginx安装配置完成。

![image-20221018143113053](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/18/20221018143113.png)







# RabbitMQ安装部署【简单】

## 简介

RabbitMQ一款知名的开源消息队列系统，为企业提供消息的发布、订阅、点对点传输等消息服务。

RabbitMQ在企业开发中十分常见，课程为大家演示快速搭建RabbitMQ环境。



## 安装

> rabbitmq在yum仓库中的版本比较老，所以我们需要手动构建yum仓库



1. 准备yum仓库

   ```shell
   # root执行
   # 1. 准备gpgkey密钥
   rpm --import https://github.com/rabbitmq/signing-keys/releases/download/2.0/rabbitmq-release-signing-key.asc
   rpm --import https://packagecloud.io/rabbitmq/erlang/gpgkey
   rpm --import https://packagecloud.io/rabbitmq/rabbitmq-server/gpgkey
   
   # 2. 准备仓库文件
   vim /etc/yum.repos.d/rabbitmq.repo
   # 填入如下内容
   ##
   ## Zero dependency Erlang
   ##
   
   [rabbitmq_erlang]
   name=rabbitmq_erlang
   baseurl=https://packagecloud.io/rabbitmq/erlang/el/7/$basearch
   repo_gpgcheck=1
   gpgcheck=1
   enabled=1
   # PackageCloud's repository key and RabbitMQ package signing key
   gpgkey=https://packagecloud.io/rabbitmq/erlang/gpgkey
          https://github.com/rabbitmq/signing-keys/releases/download/2.0/rabbitmq-release-signing-key.asc
   sslverify=1
   sslcacert=/etc/pki/tls/certs/ca-bundle.crt
   metadata_expire=300
   
   [rabbitmq_erlang-source]
   name=rabbitmq_erlang-source
   baseurl=https://packagecloud.io/rabbitmq/erlang/el/7/SRPMS
   repo_gpgcheck=1
   gpgcheck=0
   enabled=1
   # PackageCloud's repository key and RabbitMQ package signing key
   gpgkey=https://packagecloud.io/rabbitmq/erlang/gpgkey
          https://github.com/rabbitmq/signing-keys/releases/download/2.0/rabbitmq-release-signing-key.asc
   sslverify=1
   sslcacert=/etc/pki/tls/certs/ca-bundle.crt
   metadata_expire=300
   
   ##
   ## RabbitMQ server
   ##
   
   [rabbitmq_server]
   name=rabbitmq_server
   baseurl=https://packagecloud.io/rabbitmq/rabbitmq-server/el/7/$basearch
   repo_gpgcheck=1
   gpgcheck=0
   enabled=1
   # PackageCloud's repository key and RabbitMQ package signing key
   gpgkey=https://packagecloud.io/rabbitmq/rabbitmq-server/gpgkey
          https://github.com/rabbitmq/signing-keys/releases/download/2.0/rabbitmq-release-signing-key.asc
   sslverify=1
   sslcacert=/etc/pki/tls/certs/ca-bundle.crt
   metadata_expire=300
   
   [rabbitmq_server-source]
   name=rabbitmq_server-source
   baseurl=https://packagecloud.io/rabbitmq/rabbitmq-server/el/7/SRPMS
   repo_gpgcheck=1
   gpgcheck=0
   enabled=1
   gpgkey=https://packagecloud.io/rabbitmq/rabbitmq-server/gpgkey
   sslverify=1
   sslcacert=/etc/pki/tls/certs/ca-bundle.crt
   metadata_expire=300
   ```

3. 安装RabbitMQ

   ```shell
   # root执行
   yum install erlang rabbitmq-server -y
   ```
   
   ```shell
   Installed:
     erlang.x86_64 0:23.3.4.11-1.el7           rabbitmq-server.noarch 0:3.10.0-1.el7
   ```
   
4. 启动

   ```shell
   # root执行
   # 使用systemctl管控，服务名：rabbitmq-server
   systemctl enable rabbitmq-server		# 开机自启
   systemctl disable rabbitmq-server		# 关闭开机自启
   systemctl start rabbitmq-server			# 启动
   systemctl stop rabbitmq-server			# 关闭
   systemctl status rabbitmq-server		# 查看状态
   ```

5. 放行防火墙，RabbitMQ使用5672、15672、25672 3个端口

   ```shell
   # 方式1（推荐），关闭防火墙
   systemctl stop firewalld		# 关闭
   systemctl disable firewalld		# 关闭开机自启
   
   # 方式2，放行5672 25672端口
   firewall-cmd --add-port=5672/tcp --permanent		# 放行tcp规则下的5672端口，永久生效
   firewall-cmd --add-port=15672/tcp --permanent		# 放行tcp规则下的15672端口，永久生效
   firewall-cmd --add-port=25672/tcp --permanent		# 放行tcp规则下的25672端口，永久生效
   firewall-cmd --reload								# 重新加载防火墙规则
   ```

6. 启动RabbitMQ的WEB管理控制台

   ```shell
   rabbitmq-plugins enable rabbitmq_management
   ```

7. 添加admin用户，并赋予权限

   ```shell
   rabbitmqctl add_user admin 'Itheima66^'
   rabbitmqctl set_permissions -p "/" "admin" ".*" ".*" ".*"
   rabbitmqctl set_user_tags admin administrator
   ```

   

8. 浏览器打开管理控制台

   http://192.168.88.130:15672

   ![image-20221018154823983](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/18/20221018154824.png)



至此，RabbitMQ已经安装完成了。



# Redis安装部署【简单】

## 简介

redis是一个开源的、使用C语言编写的、支持网络交互的、可基于内存也可持久化的Key-Value数据库。

redis的特点就是：`快`，可以基于内存存储数据并提供超低延迟、超快的检索速度

一般用于在系统中提供快速缓存的能力。



## 安装



1. 配置`EPEL`仓库

   > EPEL 的全称叫 Extra Packages for Enterprise Linux 。EPEL是由 Fedora 社区打造，为 RHEL 及衍生发行版如 CentOS、Scientific Linux 等提供高质量软件包的项目。装上了 EPEL之后，就相当于添加了一个第三方源。EPEL则为服务器版本提供大量的rpm包(yum程序所使用的程序安装包，类似Windows的exe)，而且大多数rpm包在官方 repository 中是找不到的。

   ```shell
   # root执行
   yum install -y epel-release
   ```

2. 安装redis

   ```shell
   # root执行
   yum install -y redis
   ```

3. 启动redis

   ```shell
   # root执行
   # 使用systemctl管控，服务名：redis
   systemctl enable redis		# 开机自启
   systemctl disable redis		# 关闭开机自启
   systemctl start redis		# 启动
   systemctl stop redis		# 关闭
   systemctl status redis		# 查看状态
   ```

4. 放行防火墙，redis使用端口6379

   ```shell
   # 方式1（推荐），关闭防火墙
   systemctl stop firewalld		# 关闭
   systemctl disable firewalld		# 关闭开机自启
   
   # 方式2，放行6379端口
   firewall-cmd --add-port=6379/tcp --permanent		# 放行tcp规则下的6379端口，永久生效
   firewall-cmd --reload	
   ```

5. 进入redis服务

   ```shell
   # 执行redis-cli
   [root@centos ~]# redis-cli
   127.0.0.1:6379> set mykey hello
   OK
   127.0.0.1:6379> get mykey
   "hello"
   127.0.0.1:6379> 
   ```



至此，redis安装完成。



# ElasticSearch安装部署

## 简介

[全文搜索](https://baike.baidu.com/item/全文搜索引擎)属于最常见的需求，开源的 [Elasticsearch](https://www.elastic.co/) （以下简称 es）是目前全文搜索引擎的首选。

它可以快速地储存、搜索和分析海量数据。维基百科、Stack Overflow、Github 都采用它。



Elasticsearch简称es，在企业内同样是一款应用非常广泛的搜索引擎服务。

很多服务中的搜索功能，都是基于es来实现的。



## 安装

1. 添加yum仓库

   ```shell
   # root执行
   # 导入仓库密钥
   rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
   
   # 添加yum源
   # 编辑文件 
   vim /etc/yum.repos.d/elasticsearch.repo
   
   [elasticsearch-7.x]
   name=Elasticsearch repository for 7.x packages
   baseurl=https://artifacts.elastic.co/packages/7.x/yum
   gpgcheck=1
   gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
   enabled=1
   autorefresh=1
   type=rpm-md
   
   
   # 更新yum缓存
   yum makecache
   ```

2. 安装es

   ```shell
   yum install -y elasticsearch
   ```

3. 配置es

   ```shell
   vim /etc/elasticsearch/elasticsearch.yml
   
   # 17行，设置集群名称
   cluster.name: my-cluster
   
   # 23行，设置节点名称
   node.name: node-1
   
   # 56行，允许外网访问
   network.host: 0.0.0.0
   
   # 74行，配置集群master节点
   cluster.initial_master_nodes: ["node-1"]
   ```

4. 启动es

   ```shell
   systemctl start | stop | status | enable | disable elasticsearch
   ```

5. 关闭防火墙

   ```shell
   systemctl stop firewalld
   systemctl disable firewalld
   ```

6. 测试

   浏览器打开：http://ip:9200/?pretty

   ![image-20221025085432335](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025085432.png)







# 集群化环境前置准备

## 介绍

在前面，我们所学习安装的软件，都是以单机模式运行的。

后续，我们将要学习大数据相关的软件部署，所以后续我们所安装的软件服务，大多数都是以集群化（多台服务器共同工作）模式运行的。



所以，在当前小节，我们需要完成集群化环境的前置准备，包括创建多台虚拟机，配置主机名映射，SSH免密登录等等。

## 部署



### 配置多台Linux虚拟机

安装集群化软件，首要条件就是要有多台Linux服务器可用。

我们可以使用VMware提供的克隆功能，将我们的虚拟机额外克隆出3台来使用。

1. 首先，关机当前CentOS系统虚拟机（可以使用root用户执行`init 0`来快速关机）

2. 新建文件夹

   ![image-20221025104157628](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104157.png)

   文件夹起名为：`虚拟机集群`

3. 克隆

   ![image-20221025104131303](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104131.png)

   ![image-20221025104312091](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104312.png)

   ![image-20221025104329109](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104329.png)

   ![image-20221025104345484](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104345.png)

   ![image-20221025104414576](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104414.png)

   ![image-20221025104427160](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104427.png)

   ![image-20221025104432927](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104432.png)

   ![image-20221025104446044](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104446.png)

4. 同样的操作克隆出：node2和node3

   ![image-20221025104825204](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025104825.png)

5. 开启node1，修改主机名为node1，并修改固定ip为：192.168.88.131

   ```shell
   # 修改主机名
   hostnamectl set-hostname node1
   
   # 修改IP地址
   vim /etc/sysconfig/network-scripts/ifcfg-ens33
   IPADDR="192.168.88.131"
   
   # 重启网卡
   systemctl stop network
   systemctl start network
   # 或者直接
   systemctl restart network
   ```

6. 同样的操作启动node2和node3,

   修改node2主机名为node2，设置ip为192.168.88.132

   修改node2主机名为node3，设置ip为192.168.88.133

7. 配置FinalShell，配置连接到node1、node2、node3的连接

   > 为了简单起见，建议配置root用户登录



### 准备主机名映射

1. 在Windows系统中修改hosts文件，填入如下内容：

   > 如果同学们使用MacOS系统，请：
   >
   > 1. sudo su -，切换到root
   > 2. 修改/etc/hosts文件

   ```shell
   192.168.88.131 node1
   192.168.88.132 node2
   192.168.88.133 node3
   ```

2. 在3台Linux的/etc/hosts文件中，填入如下内容（==3台都要添加==）

   ```shell
   192.168.88.131 node1
   192.168.88.132 node2
   192.168.88.133 node3
   ```



### 配置SSH免密登录

#### 简介

SSH服务是一种用于远程登录的安全认证协议。

我们通过FinalShell远程连接到Linux，就是使用的SSH服务。

SSH服务支持：

1. 通过账户+密码的认证方式来做用户认证
2. 通过账户+秘钥文件的方式做用户认证



SSH可以让我们通过SSH命令，远程的登陆到其它的主机上，比如：

在node1执行：ssh root@node2，将以root用户登录node2服务器，输入密码即可成功登陆

或者ssh node2，将以当前用户直接登陆到node2服务器。



#### SSH免密配置

后续安装的集群化软件，多数需要远程登录以及远程执行命令，我们可以简单起见，配置三台Linux服务器之间的免密码互相SSH登陆

1. 在每一台机器都执行：`ssh-keygen -t rsa -b 4096`，一路回车到底即可

2. 在每一台机器都执行：

   ```shell
   ssh-copy-id node1
   ssh-copy-id node2
   ssh-copy-id node3
   ```

3. 执行完毕后，node1、node2、node3之间将完成root用户之间的免密互通



### 配置JDK环境

后续的大数据集群软件，多数是需要Java运行环境的，所以我们为==每一台==机器都配置JDK环境。



JDK配置参阅：`Tomcat`安装部署环节。



### 关闭防火墙和SELinux

集群化软件之间需要通过端口互相通讯，为了避免出现网络不通的问题，我们可以简单的在集群内部关闭防火墙。

==在每一台机器都执行==

```shell
systemctl stop firewalld
systemctl disable firewalld
```



Linux有一个安全模块：SELinux，用以限制用户和程序的相关权限，来确保系统的安全稳定。

SELinux的配置同防火墙一样，非常复杂，课程中不多涉及，后续视情况可以出一章SELinux的配置课程。

在当前，我们只需要关闭SELinux功能，避免导致后面的软件运行出现问题即可，

==在每一台机器都执行==

```shell
vim /etc/sysconfig/selinux

# 将第七行，SELINUX=enforcing 改为
SELINUX=disabled
# 保存退出后，重启虚拟机即可，千万要注意disabled单词不要写错，不然无法启动系统
```





### 添加快照

为了避免后续出现问题，在完成上述设置后，为==每一台虚拟机==都制作快照，留待使用。





## 补充命令 - scp

后续的安装部署操作，我们将会频繁的在多台服务器之间相互传输数据。

为了更加方面的互相传输，我们补充一个命令：scp



scp命令是cp命令的升级版，即：ssh cp，通过SSH协议完成文件的复制。

其主要的功能就是：在不同的Linux服务器之间，通过`SSH`协议互相传输文件。

只要知晓服务器的账户和密码（或密钥），即可通过SCP互传文件。



语法：

```shell
scp [-r] 参数1 参数2
- -r选项用于复制文件夹使用，如果复制文件夹，必须使用-r
- 参数1：本机路径 或 远程目标路径
- 参数2：远程目标路径 或 本机路径

如：
scp -r /export/server/jdk root@node2:/export/server/
将本机上的jdk文件夹， 以root的身份复制到node2的/export/server/内
同SSH登陆一样，账户名可以省略（使用本机当前的同名账户登陆）

如：
scp -r node2:/export/server/jdk /export/server/
将远程node2的jdk文件夹，复制到本机的/export/server/内


# scp命令的高级用法
cd /export/server
scp -r jdk node2:`pwd`/    # 将本机当前路径的jdk文件夹，复制到node2服务器的同名路径下
scp -r jdk node2:$PWD      # 将本机当前路径的jdk文件夹，复制到node2服务器的同名路径下
```











# Zookeeper集群安装部署

## 简介

ZooKeeper是一个[分布式](https://baike.baidu.com/item/分布式/19276232?fromModule=lemma_inlink)的，开放源码的[分布式应用程序](https://baike.baidu.com/item/分布式应用程序/9854429?fromModule=lemma_inlink)协调服务，是Hadoop和[Hbase](https://baike.baidu.com/item/Hbase/7670213?fromModule=lemma_inlink)的重要组件。它是一个为分布式应用提供一致性服务的软件，提供的功能包括：配置维护、域名服务、分布式同步、组服务等。



除了为Hadoop和HBase提供协调服务外，Zookeeper也被其它许多软件采用作为其分布式状态一致性的依赖，比如Kafka，又或者一些软件项目中，也经常能见到Zookeeper作为一致性协调服务存在。



Zookeeper不论是大数据领域亦或是其它服务器开发领域，涉及到分布式状态一致性的场景，总有它的身影存在。



## 安装

Zookeeper是一款分布式的集群化软件，可以在多台服务器上部署，并协同组成分布式集群一起工作。



1. 首先，要确保已经完成了`集群化环境前置准备`环节的全部内容

2. 【node1上操作】下载Zookeeper安装包，并解压

   ```shell
   # 下载
   wget http://archive.apache.org/dist/zookeeper/zookeeper-3.5.9/apache-zookeeper-3.5.9-bin.tar.gz
   
   # 确保如下目录存在，不存在就创建
   mkdir -p /export/server
   
   # 解压
   tar -zxvf apache-zookeeper-3.5.9-bin.tar.gz -C /export/server
   ```

3. 【node1上操作】创建软链接

   ```shell
   ln -s /export/server/apache-zookeeper-3.5.9 /export/server/zookeeper
   ```

4. 【node1上操作】修改配置文件

   ```shell
   vim /export/server/zookeeper/conf/zoo.cfg
   
   tickTime=2000
   # zookeeper数据存储目录
   dataDir=/export/server/zookeeper/data
   clientPort=2181
   initLimit=5
   syncLimit=2
   server.1=node1:2888:3888
   server.2=node2:2888:3888
   server.3=node3:2888:3888
   ```

5. 【node1上操作】配置`myid`

   ```shell
   # 1. 创建Zookeeper的数据目录
   mkdir /export/server/zookeeper/data
   
   # 2. 创建文件，并填入1
   vim /export/server/zookeeper/data/myid
   # 在文件内填入1即可
   ```

6. 【在node2和node3上操作】，创建文件夹

   ```shell
   mkdir -p /export/server
   ```

7. 【node1上操作】将Zookeeper 复制到node2和node3

   ```shell
   cd /export/server
   
   scp -r apache-zookeeper-3.5.9 node2:`pwd`/
   scp -r apache-zookeeper-3.5.9 node3:`pwd`/
   ```

8. 【在node2上操作】

   ```shell
   # 1. 创建软链接
   ln -s /export/server/apache-zookeeper-3.5.9 /export/server/zookeeper
   
   # 2. 修改myid文件
   vim /export/server/zookeeper/data/myid
   # 修改内容为2
   ```

9. 【在node3上操作】

   ```shell
   # 1. 创建软链接
   ln -s /export/server/apache-zookeeper-3.5.9 /export/server/zookeeper
   
   # 2. 修改myid文件
   vim /export/server/zookeeper/data/myid
   # 修改内容为3
   ```

10. 【在node1、node2、node3上分别执行】启动Zookeeper

    ```shell
    # 启动命令
    /export/server/zookeeper/bin/zkServer.sh start		# 启动Zookeeper
    ```

11. 【在node1、node2、node3上分别执行】检查Zookeeper进程是否启动

    ```shell
    jps
    
    # 结果中找到有：QuorumPeerMain 进程即可
    ```

12. 【node1上操作】验证Zookeeper

    ```shell
    /export/server/zookeeper/zkCli.sh
    
    # 进入到Zookeeper控制台中后，执行
    ls /
    
    # 如无报错即配置成功
    ```



至此Zookeeper安装完成







# Kafka集群安装部署

## 简介

Kafka是一款`分布式的、去中心化的、高吞吐低延迟、订阅模式`的消息队列系统。



同RabbitMQ一样，Kafka也是消息队列。不过RabbitMQ多用于后端系统，因其更加专注于消息的延迟和容错。

Kafka多用于大数据体系，因其更加专注于数据的吞吐能力。

Kafka多数都是运行在分布式（集群化）模式下，所以课程将以3台服务器，来完成Kafka集群的安装部署。



## 安装



1. 确保已经跟随前面的视频，安装并部署了JDK和Zookeeper服务

   > Kafka的运行依赖JDK环境和Zookeeper请确保已经有了JDK环境和Zookeeper

2. 【在node1操作】下载并上传Kafka的安装包

   ```shell
   # 下载安装包
   wget http://archive.apache.org/dist/kafka/2.4.1/kafka_2.12-2.4.1.tgz
   ```

3. 【在node1操作】解压

   ```shell
   mkdir -p /export/server			# 此文件夹如果不存在需先创建
   
   # 解压
   tar -zxvf kafka_2.12-2.4.1.tgz -C /export/server/
   
   # 创建软链接
   ln -s /export/server/kafka_2.12-2.4.1 /export/server/kafka
   ```

4. 【在node1操作】修改Kafka目录内的config目录内的`server.properties`文件

   ````shell
   cd /export/server/kafka/config
   # 指定broker的id
   broker.id=1
   # 指定 kafka的绑定监听的地址
   listeners=PLAINTEXT://node1:9092
   # 指定Kafka数据的位置
   log.dirs=/export/server/kafka/data
   # 指定Zookeeper的三个节点
   zookeeper.connect=node1:2181,node2:2181,node3:2181
   ````

5. 【在node1操作】将node1的kafka复制到node2和node3

   ```shell
   cd /export/server
   
   # 复制到node2同名文件夹
   scp -r kafka_2.12-2.4.1 node2:`pwd`/
   # 复制到node3同名文件夹
   scp -r kafka_2.12-2.4.1 node3:$PWD
   ```

6. 【在node2操作】

   ```shell
   # 创建软链接
   ln -s /export/server/kafka_2.12-2.4.1 /export/server/kafka
   
   cd /export/server/kafka/config
   # 指定broker的id
   broker.id=2
   # 指定 kafka的绑定监听的地址
   listeners=PLAINTEXT://node2:9092
   # 指定Kafka数据的位置
   log.dirs=/export/server/kafka/data
   # 指定Zookeeper的三个节点
   zookeeper.connect=node1:2181,node2:2181,node3:2181
   ```

7. 【在node3操作】

   ```shell
   # 创建软链接
   ln -s /export/server/kafka_2.12-2.4.1 /export/server/kafka
   
   cd /export/server/kafka/config
   # 指定broker的id
   broker.id=3
   # 指定 kafka的绑定监听的地址
   listeners=PLAINTEXT://node3:9092
   # 指定Kafka数据的位置
   log.dirs=/export/server/kafka/data
   # 指定Zookeeper的三个节点
   zookeeper.connect=node1:2181,node2:2181,node3:2181
   ```

8. 启动kafka

   ```shell
   # 请先确保Zookeeper已经启动了
   
   # 方式1：【前台启动】分别在node1、2、3上执行如下语句
   /export/server/kafka/bin/kafka-server-start.sh /export/server/kafka/config/server.properties
   
   # 方式2：【后台启动】分别在node1、2、3上执行如下语句
   nohup /export/server/kafka/bin/kafka-server-start.sh /export/server/kafka/config/server.properties 2>&1 >> /export/server/kafka/kafka-server.log &
   ```

9. 验证Kafka启动

   ```shell
   # 在每一台服务器执行
   jps
   ```

   ![image-20221025174522487](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/25/20221025174522.png)





## 测试Kafka能否正常使用

1. 创建测试主题

```shell
# 在node1执行，创建一个主题
/export/server/kafka_2.12-2.4.1/bin/kafka-topics.sh --create --zookeeper node1:2181 --replication-factor 1 --partitions 3 --topic test
```

2. 运行测试，请在FinalShell中打开2个node1的终端页面

```shell
# 打开一个终端页面，启动一个模拟的数据生产者
/export/server/kafka_2.12-2.4.1/bin/kafka-console-producer.sh --broker-list node1:9092 --topic test
# 再打开一个新的终端页面，在启动一个模拟的数据消费者
/export/server/kafka_2.12-2.4.1/bin/kafka-console-consumer.sh --bootstrap-server node1:9092 --topic test --from-beginning
```





# 大数据集群（Hadoop生态）安装部署

## 简介

1）Hadoop是一个由Apache基金会所开发的分布式系统基础架构。
2）主要解决，海量数据的存储和海量数据的分析计算问题。

Hadoop HDFS 提供分布式海量数据存储能力

Hadoop YARN 提供分布式集群资源管理能力

Hadoop MapReduce 提供分布式海量数据计算能力





### 前置要求

- 请确保完成了集群化环境前置准备章节的内容
- 即：JDK、SSH免密、关闭防火墙、配置主机名映射等前置操作



### Hadoop集群角色

Hadoop生态体系中总共会出现如下进程角色：

1. Hadoop HDFS的管理角色：Namenode进程（`仅需1个即可（管理者一个就够）`）
2. Hadoop HDFS的工作角色：Datanode进程（`需要多个（工人，越多越好，一个机器启动一个）`）
3. Hadoop YARN的管理角色：ResourceManager进程（`仅需1个即可（管理者一个就够）`）
4. Hadoop YARN的工作角色：NodeManager进程（`需要多个（工人，越多越好，一个机器启动一个）`）
5. Hadoop 历史记录服务器角色：HistoryServer进程（`仅需1个即可（功能进程无需太多1个足够）`）
6. Hadoop 代理服务器角色：WebProxyServer进程（`仅需1个即可（功能进程无需太多1个足够）`）
7. Zookeeper的进程：QuorumPeerMain进程（`仅需1个即可（Zookeeper的工作者，越多越好）`）





### 角色和节点分配



角色分配如下：

1. node1:Namenode、Datanode、ResourceManager、NodeManager、HistoryServer、WebProxyServer、QuorumPeerMain
2. node2:Datanode、NodeManager、QuorumPeerMain
3. node3:Datanode、NodeManager、QuorumPeerMain

![image-20221026202935745](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026202935.png)



## 安装

### 调整虚拟机内存

如上图，可以看出node1承载了太多的压力。同时node2和node3也同时运行了不少程序

为了确保集群的稳定，需要对虚拟机进行内存设置。



请在VMware中，对：

1. node1设置4GB或以上内存
2. node2和node3设置2GB或以上内存



> 大数据的软件本身就是集群化（一堆服务器）一起运行的。
>
> 现在我们在一台电脑中以多台虚拟机来模拟集群，确实会有很大的内存压力哦。



### Zookeeper集群部署

略



### Hadoop集群部署

1. 下载Hadoop安装包、解压、配置软链接

   ```shell
   # 1. 下载
   wget http://archive.apache.org/dist/hadoop/common/hadoop-3.3.0/hadoop-3.3.0.tar.gz
   
   # 2. 解压
   # 请确保目录/export/server存在
   tar -zxvf hadoop-3.3.0.tar.gz -C /export/server/
   
   # 3. 构建软链接
   ln -s /export/server/hadoop-3.3.0 /export/server/hadoop
   ```

2. 修改配置文件：`hadoop-env.sh`

   > Hadoop的配置文件要修改的地方很多，请细心

   cd 进入到/export/server/hadoop/etc/hadoop，文件夹中，配置文件都在这里

   修改hadoop-env.sh文件

   > 此文件是配置一些Hadoop用到的环境变量
   >
   > 这些是临时变量，在Hadoop运行时有用
   >
   > 如果要永久生效，需要写到/etc/profile中

   ```shell
   # 在文件开头加入：
   # 配置Java安装路径
   export JAVA_HOME=/export/server/jdk
   # 配置Hadoop安装路径
   export HADOOP_HOME=/export/server/hadoop
   # Hadoop hdfs配置文件路径
   export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop
   # Hadoop YARN配置文件路径
   export YARN_CONF_DIR=$HADOOP_HOME/etc/hadoop
   # Hadoop YARN 日志文件夹
   export YARN_LOG_DIR=$HADOOP_HOME/logs/yarn
   # Hadoop hdfs 日志文件夹
   export HADOOP_LOG_DIR=$HADOOP_HOME/logs/hdfs
   
   # Hadoop的使用启动用户配置
   export HDFS_NAMENODE_USER=root
   export HDFS_DATANODE_USER=root
   export HDFS_SECONDARYNAMENODE_USER=root
   export YARN_RESOURCEMANAGER_USER=root
   export YARN_NODEMANAGER_USER=root
   export YARN_PROXYSERVER_USER=root
   ```

3. 修改配置文件：`core-site.xml`

   如下，清空文件，填入如下内容

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
   <!--
     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at
   
       http://www.apache.org/licenses/LICENSE-2.0
   
     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License. See accompanying LICENSE file.
   -->
   
   <!-- Put site-specific property overrides in this file. -->
   <configuration>
     <property>
       <name>fs.defaultFS</name>
       <value>hdfs://node1:8020</value>
       <description></description>
     </property>
   
     <property>
       <name>io.file.buffer.size</name>
       <value>131072</value>
       <description></description>
     </property>
   </configuration>
   ```

4. 配置：`hdfs-site.xml`文件

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
   <!--
     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at
   
       http://www.apache.org/licenses/LICENSE-2.0
   
     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License. See accompanying LICENSE file.
   -->
   
   <!-- Put site-specific property overrides in this file. -->
   
   <configuration>
       <property>
           <name>dfs.datanode.data.dir.perm</name>
           <value>700</value>
       </property>
   
     <property>
       <name>dfs.namenode.name.dir</name>
       <value>/data/nn</value>
       <description>Path on the local filesystem where the NameNode stores the namespace and transactions logs persistently.</description>
     </property>
   
     <property>
       <name>dfs.namenode.hosts</name>
       <value>node1,node2,node3</value>
       <description>List of permitted DataNodes.</description>
     </property>
   
     <property>
       <name>dfs.blocksize</name>
       <value>268435456</value>
       <description></description>
     </property>
   
   
     <property>
       <name>dfs.namenode.handler.count</name>
       <value>100</value>
       <description></description>
     </property>
   
     <property>
       <name>dfs.datanode.data.dir</name>
       <value>/data/dn</value>
     </property>
   </configuration>
   ```

5. 配置：`mapred-env.sh`文件

   ```shell
   # 在文件的开头加入如下环境变量设置
   export JAVA_HOME=/export/server/jdk
   export HADOOP_JOB_HISTORYSERVER_HEAPSIZE=1000
   export HADOOP_MAPRED_ROOT_LOGGER=INFO,RFA
   ```

6. 配置：`mapred-site.xml`文件

   ```xml
   <?xml version="1.0"?>
   <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
   <!--
     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at
   
       http://www.apache.org/licenses/LICENSE-2.0
   
     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License. See accompanying LICENSE file.
   -->
   
   <!-- Put site-specific property overrides in this file. -->
   
   <configuration>
     <property>
       <name>mapreduce.framework.name</name>
       <value>yarn</value>
       <description></description>
     </property>
   
     <property>
       <name>mapreduce.jobhistory.address</name>
       <value>node1:10020</value>
       <description></description>
     </property>
   
   
     <property>
       <name>mapreduce.jobhistory.webapp.address</name>
       <value>node1:19888</value>
       <description></description>
     </property>
   
   
     <property>
       <name>mapreduce.jobhistory.intermediate-done-dir</name>
       <value>/data/mr-history/tmp</value>
       <description></description>
     </property>
   
   
     <property>
       <name>mapreduce.jobhistory.done-dir</name>
       <value>/data/mr-history/done</value>
       <description></description>
     </property>
   <property>
     <name>yarn.app.mapreduce.am.env</name>
     <value>HADOOP_MAPRED_HOME=$HADOOP_HOME</value>
   </property>
   <property>
     <name>mapreduce.map.env</name>
     <value>HADOOP_MAPRED_HOME=$HADOOP_HOME</value>
   </property>
   <property>
     <name>mapreduce.reduce.env</name>
     <value>HADOOP_MAPRED_HOME=$HADOOP_HOME</value>
   </property>
   </configuration>
   ```

7. 配置：`yarn-env.sh`文件

   ```shell
   # 在文件的开头加入如下环境变量设置
   export JAVA_HOME=/export/server/jdk
   export HADOOP_HOME=/export/server/hadoop
   export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop
   export YARN_CONF_DIR=$HADOOP_HOME/etc/hadoop
   export YARN_LOG_DIR=$HADOOP_HOME/logs/yarn
   export HADOOP_LOG_DIR=$HADOOP_HOME/logs/hdfs
   ```

8. 配置：`yarn-site.xml`文件

   ```xml
   <?xml version="1.0"?>
   <!--
     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at
   
       http://www.apache.org/licenses/LICENSE-2.0
   
     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License. See accompanying LICENSE file.
   -->
   <configuration>
   
   <!-- Site specific YARN configuration properties -->
   <property>
       <name>yarn.log.server.url</name>
       <value>http://node1:19888/jobhistory/logs</value>
       <description></description>
   </property>
   
     <property>
       <name>yarn.web-proxy.address</name>
       <value>node1:8089</value>
       <description>proxy server hostname and port</description>
     </property>
   
   
     <property>
       <name>yarn.log-aggregation-enable</name>
       <value>true</value>
       <description>Configuration to enable or disable log aggregation</description>
     </property>
   
     <property>
       <name>yarn.nodemanager.remote-app-log-dir</name>
       <value>/tmp/logs</value>
       <description>Configuration to enable or disable log aggregation</description>
     </property>
   
   
   <!-- Site specific YARN configuration properties -->
     <property>
       <name>yarn.resourcemanager.hostname</name>
       <value>node1</value>
       <description></description>
     </property>
   
     <property>
       <name>yarn.resourcemanager.scheduler.class</name>
       <value>org.apache.hadoop.yarn.server.resourcemanager.scheduler.fair.FairScheduler</value>
       <description></description>
     </property>
   
     <property>
       <name>yarn.nodemanager.local-dirs</name>
       <value>/data/nm-local</value>
       <description>Comma-separated list of paths on the local filesystem where intermediate data is written.</description>
     </property>
   
   
     <property>
       <name>yarn.nodemanager.log-dirs</name>
       <value>/data/nm-log</value>
       <description>Comma-separated list of paths on the local filesystem where logs are written.</description>
     </property>
   
   
     <property>
       <name>yarn.nodemanager.log.retain-seconds</name>
       <value>10800</value>
       <description>Default time (in seconds) to retain log files on the NodeManager Only applicable if log-aggregation is disabled.</description>
     </property>
   
   
   
     <property>
       <name>yarn.nodemanager.aux-services</name>
       <value>mapreduce_shuffle</value>
       <description>Shuffle service that needs to be set for Map Reduce applications.</description>
     </property>
   </configuration>
   ```

9. 修改workers文件

   ```shell
   # 全部内容如下
   node1
   node2
   node3
   ```

10. 分发hadoop到其它机器

   ```shell
   # 在node1执行
   cd /export/server
   
   scp -r hadoop-3.3.0 node2:`pwd`/
   scp -r hadoop-3.3.0 node2:`pwd`/
   ```

11. 在node2、node3执行

    ```shell
    # 创建软链接
    ln -s /export/server/hadoop-3.3.0 /export/server/hadoop
    ```

12. 创建所需目录

    - 在node1执行：

      ```shell
      mkdir -p /data/nn
      mkdir -p /data/dn
      mkdir -p /data/nm-log
      mkdir -p /data/nm-local
      ```

    - 在node2执行：

      ```shell
      mkdir -p /data/dn
      mkdir -p /data/nm-log
      mkdir -p /data/nm-local
      ```

    - 在node3执行：

      ```shell
      mkdir -p /data/dn
      mkdir -p /data/nm-log
      mkdir -p /data/nm-local
      ```

13. 配置环境变量

    在node1、node2、node3修改/etc/profile

    ```shell
    export HADOOP_HOME=/export/server/hadoop
    export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
    ```

    执行`source /etc/profile`生效

14. 格式化NameNode，在node1执行

    ```shell
    hadoop namenode -format
    ```

    > hadoop这个命令来自于：$HADOOP_HOME/bin中的程序
    >
    > 由于配置了环境变量PATH，所以可以在任意位置执行hadoop命令哦

15. 启动hadoop的hdfs集群，在node1执行即可

    ```shell
    start-dfs.sh
    
    # 如需停止可以执行
    stop-dfs.sh
    ```

    > start-dfs.sh这个命令来自于：$HADOOP_HOME/sbin中的程序
    >
    > 由于配置了环境变量PATH，所以可以在任意位置执行start-dfs.sh命令哦

16. 启动hadoop的yarn集群，在node1执行即可

    ```shell
    start-yarn.sh
    
    # 如需停止可以执行
    stop-yarn.sh
    ```

17. 启动历史服务器

    ```shell
    mapred --daemon start historyserver
    
    # 如需停止将start更换为stop
    ```

18. 启动web代理服务器

    ```shell
    yarn-daemon.sh start proxyserver
    
    # 如需停止将start更换为stop
    ```



#### 验证Hadoop集群运行情况

1. 在node1、node2、node3上通过jps验证进程是否都启动成功

2. 验证HDFS，浏览器打开：http://node1:9870

   创建文件test.txt，随意填入内容，并执行：

   ```shell
   hadoop fs -put test.txt /test.txt
   
   hadoop fs -cat /test.txt
   ```

3. 验证YARN，浏览器打开：http://node1:8088

   执行：

   ```shell
   # 创建文件words.txt，填入如下内容
   itheima itcast hadoop
   itheima hadoop hadoop
   itheima itcast
   
   # 将文件上传到HDFS中
   hadoop fs -put words.txt /words.txt
   
   # 执行如下命令验证YARN是否正常
   hadoop jar /export/server/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.0.jar wordcount -Dmapred.job.queue.name=root.root /words.txt /output
   ```



# 大数据NoSQL数据库HBase集群部署

## 简介

HBase 是一种[分布式](https://so.csdn.net/so/search?q=分布式&spm=1001.2101.3001.7020)、可扩展、支持海量数据存储的 NoSQL 数据库。



和Redis一样，HBase是一款KeyValue型存储的数据库。

不过和Redis设计方向不同

- Redis设计为少量数据，超快检索
- HBase设计为海量数据，快速检索

HBase在大数据领域应用十分广泛，现在我们来在node1、node2、node3上部署HBase集群。



## 安装



1. HBase依赖Zookeeper、JDK、Hadoop（HDFS），请确保已经完成前面

   - 集群化软件前置准备（JDK）
   - Zookeeper
   - Hadoop
   - 这些环节的软件安装

2. 【node1执行】下载HBase安装包

   ```shell
   # 下载
   wget http://archive.apache.org/dist/hbase/2.1.0/hbase-2.1.0-bin.tar.gz
   
   # 解压
   tar -zxvf hbase-2.1.0-bin.tar.gz -C /export/server
   
   # 配置软链接
   ln -s /export/server/hbase-2.1.0 /export/server/hbase
   ```

3. 【node1执行】，修改配置文件，修改`conf/hbase-env.sh`文件

   ```shell
   # 在28行配置JAVA_HOME
   export JAVA_HOME=/export/server/jdk
   # 在126行配置：
   # 意思表示，不使用HBase自带的Zookeeper，而是用独立Zookeeper
   export HBASE_MANAGES_ZK=false
   # 在任意行，比如26行，添加如下内容：
   export HBASE_DISABLE_HADOOP_CLASSPATH_LOOKUP="true"
   ```

4. 【node1执行】，修改配置文件，修改`conf/hbase-site.xml`文件

   ```shell
   # 将文件的全部内容替换成如下内容：
   <configuration>
           <!-- HBase数据在HDFS中的存放的路径 -->
           <property>
               <name>hbase.rootdir</name>
               <value>hdfs://node1:8020/hbase</value>
           </property>
           <!-- Hbase的运行模式。false是单机模式，true是分布式模式。若为false,Hbase和Zookeeper会运行在同一个JVM里面 -->
           <property>
               <name>hbase.cluster.distributed</name>
               <value>true</value>
           </property>
           <!-- ZooKeeper的地址 -->
           <property>
               <name>hbase.zookeeper.quorum</name>
               <value>node1,node2,node3</value>
           </property>
           <!-- ZooKeeper快照的存储位置 -->
           <property>
               <name>hbase.zookeeper.property.dataDir</name>
               <value>/export/server/apache-zookeeper-3.6.0-bin/data</value>
           </property>
           <!--  V2.1版本，在分布式情况下, 设置为false -->
           <property>
               <name>hbase.unsafe.stream.capability.enforce</name>
               <value>false</value>
           </property>
   </configuration>
   ```

5. 【node1执行】，修改配置文件，修改`conf/regionservers`文件

   ```shell
   # 填入如下内容
   node1
   node2
   node3
   ```

6. 【node1执行】，分发hbase到其它机器

   ```shell
   scp -r /export/server/hbase-2.1.0 node2:/export/server/
   scp -r /export/server/hbase-2.1.0 node3:/export/server/
   ```

7. 【node2、node3执行】，配置软链接

   ```shell
   ln -s /export/server/hbase-2.1.0 /export/server/hbase
   ```

8. 【node1、node2、node3执行】，配置环境变量

   ```shell
   # 配置在/etc/profile内，追加如下两行
   export HBASE_HOME=/export/server/hbase
   export PATH=$HBASE_HOME/bin:$PATH
   
   source /etc/profile
   ```

9. 【node1执行】启动HBase

   > 请确保：Hadoop HDFS、Zookeeper是已经启动了的

   ```shell
   start-hbase.sh
   
   # 如需停止可使用
   stop-hbase.sh
   ```

   > 由于我们配置了环境变量export PATH=$PATH:$HBASE_HOME/bin
   >
   > start-hbase.sh即在$HBASE_HOME/bin内，所以可以无论当前目录在哪，均可直接执行

10. 验证HBase

    浏览器打开：http://node1:16010，即可看到HBase的WEB UI页面

11. 简单测试使用HBase

    【node1执行】

    ```shell
    hbase shell
    
    # 创建表
    create 'test', 'cf'
    
    # 插入数据
    put 'test', 'rk001', 'cf:info', 'itheima'
    
    # 查询数据
    get 'test', 'rk001'
    
    # 扫描表数据
    scan 'test'
    ```





# 分布式内存计算Spark环境部署

## 注意

本小节的操作，基于：`大数据集群（Hadoop生态）安装部署`环节中所构建的Hadoop集群

如果没有Hadoop集群，请参阅前置内容，部署好环境。



## 简介

Spark是一款分布式内存计算引擎，可以支撑海量数据的分布式计算。



Spark在大数据体系是明星产品，作为最新一代的综合计算引擎，支持离线计算和实时计算。

在大数据领域广泛应用，是目前世界上使用最多的大数据分布式计算引擎。



我们将基于前面构建的Hadoop集群，部署Spark Standalone集群。



## 安装



1. 【node1执行】下载并解压

   ```shell
   wget https://archive.apache.org/dist/spark/spark-2.4.5/spark-2.4.5-bin-hadoop2.7.tgz
   
   # 解压
   tar -zxvf spark-2.4.5-bin-hadoop2.7.tgz -C /export/server/
   
   # 软链接
   ln -s /export/server/spark-2.4.5-bin-hadoop2.7 /export/server/spark
   ```

2. 【node1执行】修改配置文件名称

   ```shell
   # 改名
   cd /export/server/spark/conf
   mv spark-env.sh.template spark-env.sh
   mv slaves.template slaves
   ```

3. 【node1执行】修改配置文件，`spark-env.sh`

   ```shell
   ## 设置JAVA安装目录
   JAVA_HOME=/export/server/jdk
   
   ## HADOOP软件配置文件目录，读取HDFS上文件和运行YARN集群
   HADOOP_CONF_DIR=/export/server/hadoop/etc/hadoop
   YARN_CONF_DIR=/export/server/hadoop/etc/hadoop
   
   ## 指定spark老大Master的IP和提交任务的通信端口
   export SPARK_MASTER_HOST=node1
   export SPARK_MASTER_PORT=7077
   
   SPARK_MASTER_WEBUI_PORT=8080
   SPARK_WORKER_CORES=1
   SPARK_WORKER_MEMORY=1g
   ```

4. 【node1执行】修改配置文件，`slaves`

   ```shell
   node1
   node2
   node3
   ```

5. 【node1执行】分发

   ```shell
   scp -r spark-2.4.5-bin-hadoop2.7 node2:$PWD
   scp -r spark-2.4.5-bin-hadoop2.7 node3:$PWD
   ```

6. 【node2、node3执行】设置软链接

   ```shell
   ln -s /export/server/spark-2.4.5-bin-hadoop2.7 /export/server/spark
   ```

7. 【node1执行】启动Spark集群

   ```shell
   /export/server/spark/sbin/start-all.sh
   
   # 如需停止，可以
   /export/server/spark/sbin/stop-all.sh
   ```

8. 打开Spark监控页面，浏览器打开：http://node1:8081

9. 【node1执行】提交测试任务

   ```shell
   /export/server/spark/bin/spark-submit --master spark://node1:7077 --class org.apache.spark.examples.SparkPi /export/server/spark/examples/jars/spark-examples_2.11-2.4.5.jar
   ```







# 分布式内存计算Flink环境部署

## 注意

本小节的操作，基于：`大数据集群（Hadoop生态）安装部署`环节中所构建的Hadoop集群

如果没有Hadoop集群，请参阅前置内容，部署好环境。



## 简介

Flink同Spark一样，是一款分布式内存计算引擎，可以支撑海量数据的分布式计算。



Flink在大数据体系同样是明星产品，作为最新一代的综合计算引擎，支持离线计算和实时计算。

在大数据领域广泛应用，是目前世界上除去Spark以外，应用最为广泛的分布式计算引擎。



我们将基于前面构建的Hadoop集群，部署Flink Standalone集群

Spark更加偏向于离线计算而Flink更加偏向于实时计算。



## 安装



1. 【node1操作】下载安装包

   ```shell
   wget https://archive.apache.org/dist/flink/flink-1.10.0/flink-1.10.0-bin-scala_2.11.tgz
   
   # 解压
   tar -zxvf flink-1.10.0-bin-scala_2.11.tgz -C /export/server/
   
   # 软链接
   ln -s /export/server/flink-1.10.0 /export/server/flink
   ```

2. 【node1操作】修改配置文件，`conf/flink-conf.yaml`

   ```yaml
   # jobManager 的IP地址
   jobmanager.rpc.address: node1
   # JobManager 的端口号
   jobmanager.rpc.port: 6123
   # JobManager JVM heap 内存大小
   jobmanager.heap.size: 1024m
   # TaskManager JVM heap 内存大小
   taskmanager.heap.size: 1024m
   # 每个 TaskManager 提供的任务 slots 数量大小
   taskmanager.numberOfTaskSlots: 2
   #是否进行预分配内存，默认不进行预分配，这样在我们不使用flink集群时候不会占用集群资源
   taskmanager.memory.preallocate: false
   # 程序默认并行计算的个数
   parallelism.default: 1
   #JobManager的Web界面的端口（默认：8081）
   jobmanager.web.port: 8081
   ```

3. 【node1操作】，修改配置文件，`conf/slaves`

   ```shell
   node1
   node2
   node3
   ```

4. 【node1操作】分发Flink安装包到其它机器

   ```shell
   cd /export/server
   scp -r flink-1.10.0 node2:`pwd`/
   scp -r flink-1.10.0 node3:`pwd`/
   ```

5. 【node2、node3操作】

   ```shell
   # 配置软链接
   ln -s /export/server/flink-1.10.0 /export/server/flink
   ```

6. 【node1操作】，启动Flink

   ```shell
   /export/server/flink/bin/start-cluster.sh
   ```

7. 验证Flink启动

   ```shell
   # 浏览器打开
   http://node1:8081
   ```

8. 提交测试任务

   【node1执行】

   ```shell
   /export/server/flink/bin/flink run /export/server/flink-1.10.0/examples/batch/WordCount.jar
   ```







# 运维监控Zabbix部署

## 简介

Zabbix 由 Alexei Vladishev 创建，目前由其成立的公司—— Zabbix SIA 积极的持续开发更新维护， 并为用户提供技术支持服务。

Zabbix 是一个==企业级分布式开源监控解决方案==。

Zabbix 软件能够==监控==众多网络参数和服务器的==健康度、完整性==。Zabbix 使用灵活的告警机制，允许用户为几乎任何事件配置基于邮件的告警。这样用户可以快速响应服务器问题。Zabbix 基于存储的数据提供出色的报表和数据可视化功能。这些功能使得 Zabbix 成为容量规划的理想选择。



## 安装



>  安装整体步骤:

1. 准备Linux 服务器(虚拟机)
2. 安装Mysql
3. 安装zabbix( 包含 server  agent  web)
4. 配置 mysql, 为zabbix创建表结构
5. 配置zabbix server
6. 启动并开启开机自启动



![1574338996145](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175324.png)



### 安装前准备 - Mysql

安装ZabbixServer需要先安装好`Mysql`数据库

课程使用`Mysql 5.7`

安装步骤：

```shell
# 安装Mysql yum库
rpm -Uvh http://repo.mysql.com//mysql57-community-release-el7-7.noarch.rpm

# yum安装Mysql
yum -y install mysql-community-server

# 启动Mysql设置开机启动
systemctl start mysqld
systemctl enable mysqld

# 检查Mysql服务状态
systemctl status mysqld

# 第一次启动mysql，会在日志文件中生成root用户的一个随机密码，使用下面命令查看该密码
grep 'temporary password' /var/log/mysqld.log

# 修改root用户密码
mysql -u root -p -h localhost
Enter password:
 
mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'Root!@#$';

# 如果你想设置简单密码，需要降低Mysql的密码安全级别
set global validate_password_policy=LOW; # 密码安全级别低
set global validate_password_length=4;	 # 密码长度最低4位即可

# 然后就可以用简单密码了（课程中使用简单密码，为了方便，生产中不要这样）
ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';
mysql> grant all privileges on *.* to root@'%' identified by 'root';
```





### 安装Zabbix Server 和 Zabbix Agent

> 初始安装，我们先安装ZabbixServer以及在Server本机安装Agent。

打开官网下载页面：https://www.zabbix.com/download?zabbix=4.0&os_distribution=centos&os_version=7&db=mysql

![1571981197131](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175330.png)

选择对应的版本，然后再下面官网给出了具体的安装命令，使用`rpm`和`yum`来进行安装。

需要有网络。



`以下内容来自官方页面`

#### a. 安装Zabbix yum库

[documentation](https://www.zabbix.com/documentation/4.0/manual/installation/install_from_packages)

```shell
rpm -Uvh https://repo.zabbix.com/zabbix/4.0/rhel/7/x86_64/zabbix-release-4.0-2.el7.noarch.rpm
yum clean all
```

#### b. 安装Zabbix Server、前端、Agent

```shell
yum -y install zabbix-server-mysql zabbix-web-mysql zabbix-agent
# 如果只需要安装Agent的话
yum -y install zabbix-agent
```

#### c. 初始化Mysql数据库

[documentation](https://www.zabbix.com/documentation/4.0/manual/appendix/install/db_scripts)

> 在Mysql中操作

```shell
# 登录Mysql 数据库
mysql -uroot -pYourPassword
mysql> create database zabbix character set utf8 collate utf8_bin;
mysql> grant all privileges on zabbix.* to zabbix@localhost identified by 'zabbix';
# 或者: grant all privileges on zabbix.* to zabbix@'%' identified by 'zabbix';
mysql> quit;
```

测试在Zabbix Server服务器上能否远程登录Mysql，如果可以登录继续向下走。

Import initial schema and data. You will be prompted to enter your newly created password.

```shell
# zcat /usr/share/doc/zabbix-server-mysql*/create.sql.gz | mysql -uzabbix -p zabbix
```

#### d. 为Zabbix Server配置数据库

Edit file /etc/zabbix/zabbix_server.conf

```shell
DBPassword=password
DBHost=mysql-host-ip-or-hostname
```

#### e. 配置Zabbix的PHP前端

Edit file `/etc/httpd/conf.d/zabbix.conf`, uncomment and set the right timezone for you.`# php_value date.timezone Asia/Shanghai`

Start Zabbix server and agent processes and make it start at system boot:

```shell
systemctl restart zabbix-server zabbix-agent httpd # 启动、重启
systemctl enable zabbix-server zabbix-agent httpd  # 开机自启
```

Now your Zabbix server is up and running!



### 配置zabbix 前端（WEB UI）

**打开:`http://192.168.88.131/zabbix`**

即可进入Zabbix页面，在首次打开的时候，会进入设置页面，如图：

![1571993951841](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175338.png)

**点击下一步，会检查相应的设置是否都正常**

![1571994018126](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175341.png)

如果一切正常，点击下一步。



**配置DB连接**

![1571994069689](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175344.png)

按具体情况填写即可



**配置Server细节**

![1571994111921](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175347.png)



具体配置即可，Name表示这个Zabbix服务的名字，这里起名叫`ITHEIMA-TEST`



**安装前总结预览**

检查确认没有问题就下一步

![1571994206902](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175349.png)

**配置完成**

![1571994221531](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175351.png)



**初始管理员账户Admin密码zabbix**



输入账户密码后，就能进入zabbix页面了。

如下图：

![1571994287036](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175354.png)

现在是一个崭新的zabbix等待我们去探索。









# 运维监控Grafana部署

## 简介



## 安装

### 部署形式

`Grafana`支持两种部署形式

1. 自行部署, 可以部署在操作系统之上. 自行提供服务器, 域名等.
2. `Grafana`官方托管. 无需安装, 在线注册即可得到一个专属于自己的`Grafana`, 但是要花钱的. 是一种`SaaS`服务

我们课程选择方式1

### 安装

`Grafana`支持常见的绝大多数操作系统, 如`windows` `mac` `linux` 同时也支持部署在`docker`中.

大多数情况下, `Grafana`都是部署在`linux`服务器之上. 所以本课程也是基于`Linux`系统来讲解.

对`windows` `mac`系统 或 `docker`部署有兴趣的同学, 请参考:  https://grafana.com/grafana/download



我们部署`Grafana`可以使用`YUM`来进行部署.

```shell
# 创建一个文件
vim /etc/yum.repos.d/grafana.repo

# 将下面的内容复制进去
[grafana]
name=grafana
baseurl=https://packages.grafana.com/oss/rpm
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://packages.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt

# 最后安装
yum install grafana
```



### 配置说明

`grafana-server`具有许多配置选项，这些选项可以在`.ini`配置文件中指定，也可以使用环境变量指定。

>  **Note.** `Grafana ` needs to be restarted for any configuration changes to take effect. 

#### 配置文件注释

`;`符号在`.ini`文件中全局表示注释 ()

#### 配置文件路径

如果是自己解压安装, 或者自行编译的方式安装, 配置文件在:

- 默认: `$WORKING_DIR/conf/defaults.ini`
- 自定义:`$WORKING_DIR/conf/custom.ini`
- 自定义配置文件路径可以被参数`--config`覆盖

> 对于`YUM` `RPM` 安装的方式, 配置文件在: `/etc/grafana/grafana.ini`

#### 使用环境变量

可以使用以下语法使用环境变量来覆盖配置文件中的所有选项：

```bash
GF_<SectionName>_<KeyName>
```

其中`SectionName`是方括号内的文本。一切都应为大写，`.`应替换为`_` 例如，给定以下配置设置：

```bash
# default section
instance_name = ${HOSTNAME}

[security]
admin_user = admin

[auth.google]
client_secret = 0ldS3cretKey
```

Then you can override them using:

```bash
export GF_DEFAULT_INSTANCE_NAME=my-instance
export GF_SECURITY_ADMIN_USER=true	# GF_ 固定 SECURITY 是SectionName ADMIN_USER 是配置的key 转大写 . 转 _
export GF_AUTH_GOOGLE_CLIENT_SECRET=newS3cretKey
```



### 开始配置

`Grafana`支持使用`Sqlite3` `Postgresql` `Mysql`这三种数据库作为其`元数据`的存储.

我们课程使用`Mysql`. 和`zabbix`的元数据mysql共用一个实例

只需要配置如下内容即可:

![1573635500521](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/10/26/20221026175713.png)

并登陆mysql, 执行:

`create database grafana CHARACTER SET utf8 COLLATE utf8_general_ci;`

创建`Grafana`使用的数据库作为元数据存储.

### 启动

```bash
systemctl daemon-reload
systemctl start grafana-server
systemctl enable grafana-server
```





浏览器打开：http://node1:3000

默认账户密码：admin/admin

































