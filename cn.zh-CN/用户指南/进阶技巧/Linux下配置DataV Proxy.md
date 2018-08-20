# Linux下配置DataV Proxy {#concept_w2c_3fq_p2b .concept}

使用 DataV 数据代理服务，无需数据库打开权限，也无需编写 API，就可以配置更安全的数据查询。它将加密的 SQL 查询字符串和数据库 ID 值传递给应用程序，然后由该应用程序连接到数据库，获取查询结果并将其返回到 DataV 页面。

单击[此处](https://files.alicdn.com/tpsservice/ff301b57189c503f06eff0a649cf4e20.zip)，下载 GitHub 上发布的一个示例应用程序，可将其部署到 ECS 实例中。

您可以使用此 Node.js 示例应用程序，也可以开发一个新的应用程序。

## 操作步骤 {#section_owz_vn1_r2b .section}

1.  购买 ECS 服务器。可以使用最低配置，后续可以根据需要升级。
2.  部署代码并启动服务。
3.  配置数据库。
4.  配置到 DataV。

1.  **购买 ECS 服务器**

    进入ECS购买页，根据以下提示完成购买。

    -   选择**计费方式**为**按量计费**。
    -   选择**镜像**为**公共镜像**，并选择 **CentOS 7.4 64-bit**。
    -   建议选择**公网带宽**为**按使用流量**。
    -   如果没有特殊要求，则不需要数据盘。
    -   请根据系统提示，选择其它配置并完成购买。
2.  **部署代码并启动服务**

    Linux系统下执行如下命令，下载代码包。

    ```
    wget https://codeload.github.com/ericdum/DataVProxy/zip/master
    unzip master
    cd DataVProxy-master
    ```

    执行如下命令，部署服务。

    ```
    make install
    ```

    结果如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/15347451358646_zh-CN.png)

    请保存上图红色框中的信息，您会在下一步用到该信息。

    -   如果忘记，可运行 node ./bin/info.js 命令再次查看该信息。
    -   如果需要更改密钥，可运行 node ./bin/genkv.js 命令生成一个新的密钥。
    -   如果您在红框下看到应用程序状态信息，说明该应用程序已成功激活。
    -   可以访问`http://域名:端口/status`验证服务器状态。

        根据上述输出，您可以访问 `http://115.29.246.129:9998/status`。

3.  **配置数据库**

    打开 config.js ，在 databases 数组中仿照示例增加数据库，如下所示。

    ```
    databases: [
        {
          id: 'test',        // 确保没有任何重复的 ID。然后将其填充到 DataV 后端“数据库”字段中。 
          type: 'mysql',     // rds, ads
          host: '127.0.0.1', // 域名和 IP 地址
          user: 'root',      // 用户名
          password: 'root',  // 密码
          database: 'test',  // 数据库名称
          port: 3306         // 端口
        },
        {
          // ... 
        },
        // ...在这里填写您要添加的数据库。 
      ]
    ```

4.  **配置到 DataV**

    1.  在DataV控制台上，选择**我的数据** \> **添加数据**。
    2.  在**新建数据**页面，选择**类型**为**DataV数据代理服务**。
    3.  将上文中红框中的信息填入下图的输入框中，参数详情请参考[DataV 数据代理服务](https://www.alibabacloud.com/help/zh/doc-detail/59774.html)。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/15347451359303_zh-CN.png)

    4.  在项目的数据配置中，选择**数据源类型**为**数据库**，数据库选择上图自定义的数据源。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/15347451358648_zh-CN.png)

    **说明：** 

    -   该服务 SDK 只提供 HTTP 服务。如果您需要使用 HTTPS 服务，则需要申请一个 Chrome 认可的 HTTPS 证书，申请方法请在谷歌浏览器中搜索。
    -   在有 HTTPS 服务之前，请确保 DataV 页面是使用 HTTP 协议打开的。（该策略可确保 HTTPS 网站的安全）

## 运营和维护 {#section_v3y_x41_r2b .section}

-   执行如下命令，检查实时日志。

    ```
    pm2 logs
    ```

-   执行如下命令，检查历史日志。

    ```
    ls -al ./DataVProxy-master/logs
    ```

-   执行如下命令，重启服务器。

    ```
    pm2 restart all
    ```

-   执行如下命令，启动服务。

    ```
    pm2 start app.js
    ```


