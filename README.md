### 功能描述
本模板用于通过寄云 PaaS 平台，在您的私有 / 公有云快速搭建 PHP 应用运行环境；简化您的程序代码的上传配置流程；根据负载及系统资源使用情况，自动伸缩应用节点的数量，轻松实现自动运维。

### 操作步骤
1. 指定您的云账户信息；
2. 指定运行应用环境的主机配置信息；
3. 指定您的程序代码获取路径；（目前支持通过 GitHub 项目路径获取，和通过 URL 获取 zip 源码包两种方式）  
`https://github.com/neucloud-ncae/ncae-example-php`  
`http://neucloud.oss-cn-beijing.aliyuncs.com/softwares/ncae/ncae-example-php-master.zip`
4. 指定您程序后端数据库的连接信息：数据库地址、数据库库名、数据库用户、数据库密码；（此步骤可选，这些选项默认为空值）
5. 执行部署操作；
6. 部署执行成功后，根据平台提供的方式登录服务器，完成您所上传应用的后续配置。

### 常见问题
如何配置数据库连接？
> 您之前所填写的数据库连接信息，都在应用服务器中以环境变量的形式进行了映射，其对应关系：  
数据库地址：`DB_ADDR`  
数据库库名：`DB_NAME`  
数据库用户：`DB_USER`  
数据库密码：`DB_PASSWORD`

如何处理 PHP 的库依赖关系？
> 我们已经在应用服务器内预置了 composer 依赖管理工具，如果您已经在项目中通过 composer.json 声明了程序所依赖的外部库关系，可以直接在项目路径下执行类似这样的命令调用 composer 自动处理依赖关系：
```
$ /usr/local/bin/composer.phar install
```

程序目录调整？
> 项目下载（或源码包解压）后将被放置于 `/var/www/html` 路径下，同时 Apache 的 Index 也将指向该路径，请您自行根据项目的路径结构调整相关配置。
