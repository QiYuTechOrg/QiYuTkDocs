.. _server_deploy_prod:

.. meta::
   :description: 奇遇淘客服务器端生产环境部署文档。
   :keywords: 奇遇淘客服务器端部署, 开源淘宝客导购, 淘宝客开源源码, 淘宝客源码 开源, 淘宝客优惠券开源源码, 淘宝客全开源版源码, 淘宝客开源框架, 奇遇淘客服务器端


生产环境部署
====================================

.. note::

    遇到问题可以参见 :ref:`服务器端部署 <server_deploy_faq>` 说明

.. warning::

    生产环境不建议您在 *docker* 中运行 *PostgreSQL* 数据库。

================
生产环境部署
================

快速部署教程

#. 复刻部署代码 :code:`git clone https://github.com/QiYuTechOrg/QiYuTkDeploy`
#. 构建本地 Docker 镜像 :code:`cd QiYuTkDeploy && docker-compose build`
#. 手工编辑 :code:`envs/custom.env` 配置文件
#. :code:`docker-compose up -d` 启动服务

详细流程如下:

获取部署代码仓库
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#. 复刻部署代码仓库

    .. code-block:: bash

        git clone https://github.com/QiYuTechOrg/QiYuTkDeploy

#. 构建本地镜像的命令

    .. code-block:: bash

        docker-compose build

.. tip::

    如果您在中国可以参见 :ref:`Docker 镜像 <server_docker>` 使用阿里云的镜像以加速下载。


环境变量配置
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:ref:`环境变量参考 <server_env>`


* *envs/shared.env* 可以不用修改
* *envs/custom.env* 里面的项目必须配置

启动服务
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: bash

    docker-compose up


启动之后可以使用 :code:`docker-compose ps` 检查运行状态。

显示以下信息则表示运行正常:

.. code-block:: bash

    $ docker-compose ps
      Name                 Command                 State                   Ports
    -----------------------------------------------------------------------------------------
    tbk_admin   /app/entrypoints/admin.sh       Up (healthy)   0.0.0.0:8001->8001/tcp,
                                                               8002/tcp
    tbk_cron    /app/entrypoints/cron.sh        Up             8001/tcp, 8002/tcp
    tbk_db      docker-entrypoint.sh postgres   Up             5432/tcp

还可以使用 :code:`curl http://127.0.0.1:8001/` 访问服务器, 查看是否返回信息。

.. note::

    如果您想通过公网 IP 访问(例如: http://1.1.1.1:8001), 请确保您的 8001 端口已经开放。

    大多数云服务器厂商的防火墙默认关闭这两个端口(您也可以通过修改 docker-compose.yaml 配置来使用别的端口)。


.. note::

    如果您想通过域名访问，您必须配置反向代理, 代码仓库中有 Caddy 和 Nginx 的配置例子。

.. important::

    生产环境中推荐使用 Caddy 服务器，因为它可以自动获取 HTTPS 证书, 而且配置复杂度比 Nginx 低。

启动之后
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. title:: 添加管理员

#. 使用 :code:`docker ps` 找到 *tbk_admin* 服务，
#. 执行: :code:`docker exec -it ${DOCKER_NAME} bash`
#. 使用 :code:`python manage.py createsuperuser` 创建管理员账号
#. 浏览器打开后台管理页面, 登录管理后台。

.. note::

    Web 界面示例: `https://www.taidimall.com/ <https://www.taidimall.com/>`_

    管理后台示例: `https://www.taidimall.com/admin <https://www.taidimall.com/admin>`_

    部署之后可以通过访问 OpenAPI 文档页面来进行接口的测试, 例如: 您的域名文 www.taidimall.com
    则可以访问 `https://www.taidimall.com/api/docs <https://www.taidimall.com/api/docs>`_ 然后在网页上调试接口。

