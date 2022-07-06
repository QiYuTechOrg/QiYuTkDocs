.. _android_self_host:

.. meta::
   :description: 怎么样编译自己的奇遇淘客版本
   :keywords: 奇遇淘客编译

构建您自己的APK
========================================


========================================
配置您自己的域名
========================================

编辑 :code:`app/build.gradle` 文件, 使用您的域名替换 :code:`www.taidimall.com` 即可


示例
~~~~~~~~~~~~~~~~~

例如使用 :code:`demo.tbk` 域名则配置应该为:

.. code-block:: groovy

    buildConfigField 'String', 'ADMIN_URL', '"https://demo.tbk"'
    buildConfigField 'String', 'BASE_URL', '"https://demo.tbk/api"'


============================
阿里百川安全图
============================

如果您需要使用您自己的 PID，那么构建 APK 的时候，需要使用您自己的安全图, 否则会导致百川初始化失败。

:ref:`淘宝开放平台申请 <tbk_index>`

`阿里百川官方文档 <https://developer.alibaba.com/docs/doc.htm?treeId=129&articleId=118101&docType=1>`_

============================
允许 HTTP 协议访问服务器
============================

.. note::

    如果您使用 HTTPS 协议 则不需要此配置

为了 APP 的安全我们通常使用 HTTPS 协议，对于需要使用 HTTP 协议的用户来说，在高版本的 Android 上运行的时候，需要配置 Android 配置项:
`启用 HTTP 协议 <https://developer.android.com/guide/topics/manifest/application-element#usesCleartextTraffic>`_

.. code-block:: bash

    android:usesCleartextTraffic = true

