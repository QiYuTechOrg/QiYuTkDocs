.. _tbk_index:

.. meta::
   :description: 淘宝客账号注册教程. 淘宝客是一种按成交计费的推广模式,也指通过推广赚取收益的一类人,淘宝客就是指帮助卖家推广商品并获取佣金的人。
   :keywords: 淘宝客, 淘宝开发平台, 怎么申请淘宝客账号, 哪里申请淘宝客账号密码, 淘宝账号怎么申请淘宝客

淘宝开放平台申请
==========================

这篇文章是您开启淘宝客流程的第一步:

    主要回答 淘宝账号怎么申请淘宝客 这个问题。


只要您想做 淘宝客 (APP、网页、小程序等等)推广, 那么从淘宝开放平台申请 账号 和 相应的权限 则是开启您淘客旅程的第一步。


.. note::

    不幸的是，从淘宝开放平台申请账号及相应的权限不怎么简单。



=====================
淘宝联盟申请
=====================


媒体备案管理 申请
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

首先进入 `淘宝联盟的官方网站 <https://pub.alimama.com/>`_ , 使用您自己的淘宝账号登录就可以。

* 登录之后点击进入后台。
* 然后点击推广管理。

如图所示:

.. thumbnail:: /_static/tbk/tbk/淘宝联盟-推广管理.png

然后点击新增媒体备案添加一个新的媒体备案就可以了。

.. tip::

    申请的时候有审核,申请自有平台(自有平台要求提供的信息比较多)不通过,可以申请他方平台试试。


渠道管理 申请 渠道专属推广位
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. warning::

    您必须完成 媒体备案管理 申请之后才能进行这一步的操作。

    申请的是 *渠道专属推广位* ，不是 *推广者备案* 中的 *推广位管理* 。


如图所示:

.. thumbnail:: /_static/tbk/tbk/淘宝联盟-专属推广位.png


申请下来之后 这个 PID 就是 渠道专属 PID。



============================================
阿里百川 开发者控制台 申请
============================================

前往 `阿里百川 开发者控制台 <https://console.baichuan.taobao.com/>`_

登录之后创建应用:

.. thumbnail:: /_static/tbk/tbk/阿里百川-创建应用.png


.. note::

    在开发您的 APP 的时候，需要的 安全图片 就是从这儿获取。

创建应用之后需要申请 API 权限，点击 *API申请*, 把允许申请的都申请了。


进入 *套件申请* ，把允许申请的都申请了。
进入 *我的产品后台* ，申请 百川电商SDK 。

============================================
淘宝联盟 开放平台 申请
============================================

进入 `淘宝联盟 开发平台 <https://aff-open.taobao.com/>`_

登录之后 创建应用:

.. thumbnail:: /_static/tbk/tbk/淘宝联盟-开发平台-联盟申请.png


创建应用之后 需要申请 APPKey, 申请 APPKey 之后 进入 APP 的 功能场景,

需要申请 淘宝客【公用】私域用户管理 权限(这样才能允许绑定渠道ID)。

.. hint::

    权限越多越好哦


.. _tbk_index_cb_url:

===========================
淘宝开放平台配置
===========================

登录 `淘宝开放平台 <https://console.open.taobao.com/>`_ , 在应用管理里面找到您在 阿里百川 开发者中心创建的应用。

点击 :code:`管理`, 然后选择 :code:`应用设置 -> 基本信息`:

如图所示:

.. thumbnail:: ./淘宝开放平台.png

修改回调 URL 为您服务器的URL(然后保存)。
