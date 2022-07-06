.. _server_env:

.. meta::
   :description: 奇遇淘客服务器端配置环境变量
   :keywords: 奇遇淘客服务器Docker镜像, Docker 镜像, 奇遇淘客 Docker, 奇遇淘客服务器端


服务器环境变量
====================================

==========================
Django 配置
==========================

DJANGO_SERVE_STATIC_FILES
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

使用 Django 托管 *static* 静态文件.

.. note::

    如果您的网站流量比较小，可以使用 Django 托管静态文件。

    如果您的网站流量比较大，建议使用 Web 服务器直接托管静态文件。

    如果您的网站流量非常大，建议使用 CDN 服务托管静态文件。


.. hint::

    在 docker 环境中 配置为: /app/static 即可

DJANGO_SERVE_MEDIA_FILES
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

使用 Django 托管 *media* 静态文件.

.. note::

    如果您的网站流量比较小，可以使用 Django 托管静态文件。

    如果您的网站流量比较大，建议使用 Web 服务器直接托管静态文件。

    如果您的网站流量非常大，建议使用 CDN 服务托管静态文件。


.. hint::

    在 docker 环境中 配置为: /app/media 即可

DJANGO_SECRET_KEY
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Django 秘密字符串。最好字符串的长度为 64 字节以上。

例如:

.. code-block:: text

    j_U76BkXOcdAm26tXhJk3dv9W_NnOnp0CTqTsmo80F3GbbBzGxx_BlbzF67Jmoju

.. warning::

    没有配置会弱化系统的安全性。

DJANGO_ALLOWED_HOSTS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

允许访问的域名列表, 多个域名使用 ; 分隔

配置示例:

.. code-block:: text

    www.taidimall.com;api.taidimall.com

.. warning::

    默认配置为允许任何域名访问。

DJANGO_CSRF_TRUSTED_ORIGINS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

允许跨域的 URL 列表, 多个使用 ; 分隔。

`Django 文档 <https://docs.djangoproject.com/en/4.0/ref/settings/#csrf-trusted-origins>`_

配置示例:

.. code-block:: text

    https://www.taidimall.com;http://127.0.0.1


DJANGO_LANGUAGE_CODE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Django 默认语言配置, 默认为 简体中文，一般不需要更改。


DJANGO_TIME_ZONE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Django 时区配置，默认为 上海时区，一般不需要更改。


========================
数据库配置
========================

DB_USE_SQLITE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

使用 SQLite 作为数据库

.. warning::

    启用 SQLite 之后不再需要配置其他数据库，对于 开发 & 体验 & 中小网站推荐使用此配置。


DB_ENGINE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

数据库引擎, 默认使用 *PostgreSQL*

默认配置:

.. code-block:: text

    django.db.backends.postgresql

DB_NAME
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

数据库名称

DB_USER
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

数据库用户名

DB_PASSWORD
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

连接数据库使用的密码

DB_HOST
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
数据库的 域名/IP 地址

DB_PORT
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
数据库的端口号

====================
淘宝客配置
====================

ALI_INVITE_CODE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
邀请码

ALI_PID
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

渠道 PID

.. warning::

    必须是渠道专属 PID

ALI_APP_KEY
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

淘宝开发平台 APP Key

ALI_APP_SECRET
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

淘宝开发平台 APP Secret

====================
大淘客配置
====================

DTK_APP_KEY
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

大淘客 APP Key

DTK_APP_SECRET
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

大淘客 APP Secrets

====================
折淘客配置
====================

ZTK_SID
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
折淘客 SID

ZTK_APP_KEY
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

折淘客 App key

====================
WebHook 配置
====================

WEBHOOK_NEW_ORDER
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

新订单的 WebHook 通知

通知的字段如下:

.. code-block:: javascript

    {
        "username": "str 用户名",
        "income": "float 预估佣金",
        "item": {
            "title": "str 商品标题",
            "pic": "str 商品图片",
            "price": "float 商品原价",
        },
        "pay": {
            "price": "float 支付的价格",
            "time": "str 支付的时间",
        },
        "order_no": "str 订单 ID",
        "shop_title": "str 商家名称",
    }


WEBHOOK_NEW_USER
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

新用户的 WebHook 通知

通知的字段如下:

.. code-block:: javascript

    {"username": "str 用户名称"}

WEBHOOK_NEW_BIND
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

用户绑定渠道ID的通知

通知的字段如下:

.. code-block:: javascript

    {
        "username": "str 用户名",
        "relation_id": "str 渠道ID",
        "special_id": "str 关系ID",
        "ctime": "str 绑定时间",
    }

====================
杂项配置
====================

ADMIN_HOST
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

管理访问域名, 必须填写, Android版本的APP绑定渠道 ID 的时候需要。

一般情况这个值应该是 ALLOWED_HOSTS 中的一个。

示例:

.. code-block:: text

    www.taidimall.com


WEB_SHOW_COUPON
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Web 界面是否展示佣金
