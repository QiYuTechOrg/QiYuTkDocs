.. _server_deploy_faq:

.. meta::
   :description: 奇遇淘客服务器端部署常见问题。
   :keywords: 奇遇淘客服务器端部署, 开源淘宝客导购, 淘宝客开源源码, 淘宝客源码 开源, 淘宝客优惠券开源源码, 淘宝客全开源版源码, 淘宝客开源框架, 奇遇淘客服务器端


常见问题列表 (FAQ)
====================================

=====================================
怎么样测试服务器是否正常?
=====================================

.. note::

    这里假设您使用的域名为: www.taidimall.com

#. 访问 `https://www.taidimall.com/ <https://www.taidimall.com/>`_ 查看页面是否正常
#. 访问 `https://www.taidimall.com/api/docs <https://www.taidimall.com/api/docs>`_ 测试里面的接口是否正常

=====================================
docker-compose.yaml 文件无效
=====================================

使用 :code:`docker-compose up` 命令启动的时候显示如下错误信息:

.. code-block:: text

    ERROR: The Compose file './docker-compose.yaml' is invalid because:
    services.api.depends_on contains an invalid type, it should be an array
    services.cron.depends_on contains an invalid type, it should be an array
    services.admin.depends_on contains an invalid type, it should be an array

解决方法:

docker-compose.yaml 文件实际上是有效的，可能因为您使用的 docker-compose 版本过低导致的。

可以使用 :code:`pip3 install docker-compose --upgrade --user` 命令升级 docker-compose 版本。

=====================================
pip3 命令不存在
=====================================

解决方法: 使用系统包管理工具手动安装。

* RedHat/CentOS 使用 :code:`yum install python3-pip`
* Debian/Ubuntu 使用 :code:`apt install python3-pip`

