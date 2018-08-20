# 配置VPC数据源 {#concept_o1n_tj1_r2b .concept}

DataV 数据可视化支持将 VPC 内的数据库配置为数据源，VPC的相关概念请参见[VPC文档](https://www.alibabacloud.com/help/zh/product/27706.html)。

1.  进入[DataV控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉箭头，选择数据库类型为**RDS for MySQL**。
3.  单击下拉箭头，选择**内网**。
4.  打开**VPC（专有网络）**开关，并填写数据库信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15347451239304_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15347451239305_zh-CN.png)

    除了传统的数据库配置外，还需要配置 VPC 数据库的 VPC ID 和实例 ID。这两种 ID 都可以在阿里云控制台找到。

    -   通过RDS控制台获取实例 ID 和 VPC ID。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15347451238636_zh-CN.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15347451238637_zh-CN.png)

    -   如果您的数据库是安装在 VPC 内的 ECS 上，则需要配置该 ECS 的 VPC ID 和实例 ID。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15347451248638_zh-CN.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15347451248639_zh-CN.png)

5.  单击**测试连接**，验证数据库是否能连通正常。
6.  测试连接通过后，单击**完成**，完成数据源添加。

配置完成后您就可以使用该 VPC 的数据库作为组件的数据源了。

