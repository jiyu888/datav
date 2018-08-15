# 添加兼容 MySQL 数据库的数据源 {#concept_vt5_flp_p2b .concept}

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  进入[DataV控制台](https://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为**兼容 MySQL 数据库**。
3.  填写数据库信息

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16537/15343028357910_zh-CN.png)

    -   名称：数据源的显示名称，可以自由命名。
    -   域名：连接数据库的 URL 地址（不是官网页面的 URL，也不是本机的 IP，是需要 DataV 服务器能够通过公网或阿里云部分 Region 内网访问您数据库的 URL 地址）。
    -   用户名：登录数据库的用户名。
    -   密码：登录数据库的密码。
    -   端口：数据库设置的端口。
    -   数据库：当前所选数据库的名称。
    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

4.  测试成功后，单击**确认**，完成数据源添加。

