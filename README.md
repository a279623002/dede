# dede
通常我们在本地开发完成后，要上传到服务器上部署，我本地是部署在localhost/test下面的，下面是我上传的步骤。

1. 通过phpMyAdmin导出数据库，包括了数据表创建和数据插入的sql.

     这里有两个地方要注意：

     1） 有的空间提供的数据库是建好的，我们不能建新库，也不能改库名，而这个sql里面第一句是检查库是否存在， 不存在则创建，这里这个库名要改成空间提供的这个数据库的名字。

      2）我本地是mysql5.6,服务器上是mysql5.0，有一个地方不兼容，要修改

              KEY `pkey` (`pkey`) USING BTREE 改成  KEY `pkey` USING BTREE  (`pkey`) 



2. 把dedecms整个文件夹上传到服务器上的根目录下。

3. 修改数据库配置文件data/common.inc.php

4. 登录dedecms后台，修改系统->核心设置下面的安装目录，设置为空即可，因为我们是安装在根目录下，而我本地是安装在test目录下，所以这里设置为test. 之前没有改这里导致模板怎么都找不到。

5.重新生成所有页面和文档即可正常访问。

详细见 https://jingyan.baidu.com/article/fc07f98902d47a12fee51979.html
----
