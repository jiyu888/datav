# 创建RDS for MySQL数据库表 {#task_srh_hxh_ffb .task}

1.  登录阿里云[云数据库RDS控制台](https://rdsnext.console.aliyun.com)。 
2.   单击**创建实例**，创建RDS for MySQL实例。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21748/153803075012612_zh-CN.png)

 
3.  单击左侧菜单栏的**账号管理**，创建账号。 
4.  单击左侧菜单栏的**数据库管理**，创建数据库。 
5.  单击左侧菜单栏的**数据安全性**，参考[白名单配置](https://help.aliyun.com/document_detail/72977.html)，添加数据库白名单。 
6.  单击左侧菜单栏的**基本信息**，获取RDS实例的基本信息。此信息需要填入Datahub的DataConnector中，用于同步数据到RDS for MySQL。 
7.  单击**基本信息**页面右上角的**登录数据库**，输入账号和密码，进入DMS系统。 
8.  创建表mytable，包含两个字段，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21748/153803075012615_zh-CN.png)

 

