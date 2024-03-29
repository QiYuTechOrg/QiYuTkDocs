.. _server_release:

.. meta::
   :description: 奇遇淘客服务器端发布版本记录。
   :keywords: 奇遇淘客服务器端部署, 开源淘宝客导购, 淘宝客开源源码, 淘宝客源码 开源, 淘宝客优惠券开源源码, 淘宝客全开源版源码, 淘宝客开源框架, 奇遇淘客服务器端


发布记录
====================================

======================
v0.8.5
======================

发布日期: 2022/10/20

* 升级 Python 版本
* 升级 Django 版本
* 修正备案URL地址
* 代码修正
* 添加 python stub

======================
v0.8.4
======================

发布日期: 2022/7/7

* 升级 Django 版本[避免 SQL 注入问题]

======================
v0.8.3
======================

发布日期: 2022/6/25

* 升级依赖版本

======================
v0.8.1
======================

发布日期: 2022/2/10

* 添加 DJANGO_CSRF_TRUSTED_ORIGINS 配置 (Django 4.0 需要)

======================
v0.8.0
======================

发布日期: 2022/2/10

* 添加 多语言 支持 (英语)
* 支持生产环境使用 SQLite

======================
v0.6.1
======================

发布日期: 2022/1/3

* 添加 Django 模版变量类型声明
* 升级相关依赖

======================
v0.6.0
======================

发布日期: 2021/12/9

* 静态文件使用 jsdelivr CDN

======================
v0.5.11
======================

发布日期: 2021/10/11

* 日常维护,升级依赖

======================
v0.5.10
======================

发布日期: 2021/10/6

* 日常维护,升级依赖

======================
v0.5.9
======================

发布日期: 2021/9/22

* 日常维护

======================
v0.5.8
======================

发布日期: 2021/8/30

* 修正获取不到数据导致接口错误的问题

======================
v0.5.7
======================

发布日期: 2021/8/24

* 更新依赖

======================
v0.5.6
======================

发布日期: 2021/7/8

* 网页端支持搜索淘口令

======================
v0.5.5
======================

发布日期: 2021/7/7

* 修正 WebHook 等一些小问题

======================
v0.5.0
======================

发布日期: 2021/7/2

* 移除 dataclasses_json 依赖
* 添加 WebHook 支持
* 网页端支持展示佣金

======================
v0.4.6
======================

发布日期: 2021/7/1

* 修正高佣转换错误

======================
v0.4.5
======================

发布日期: 2021/6/28

* 修正 API 获取数据错误

======================
v0.4.3
======================

发布日期: 2021/6/13

* 依赖更新

======================
v0.4.2
======================

发布日期: 2021/6/1

* 更新依赖版本解决 `pydantic <https://github.com/samuelcolvin/pydantic/security/advisories/GHSA-5jqp-qgf6-3pvh>`_ 潜在的安全问题


======================
v0.4.1
======================

发布日期: 2021/5/6

* 使用 NinjaAPI 替换 FastAPI (https://github.com/QiYuTechOrg/QiYuTkServer/pull/3)

这样就不再需要两个域名来运行淘宝客服务。

======================
v0.4.0
======================

发布日期: 2021/4/8

* 升级到 Django 3.2

获取新版本的镜像直接升级即可。

没有兼容性问题。

升级流程
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: bash

    # 获取最新版本的部署代码
    git clone https://github.com/QiYuTechOrg/QiYuTkDeploy
    # 升级 Docker 版本
    docker-compose build --no-cache && docker-compose up -d

======================
v0.3.3
======================

发布日期: 2021/4/3

* 新增部署代码
* 更新依赖版本


======================
v0.3.0
======================

发布日期: 2021/3/6

* 新增加 Web UI
* 移除/优化废弃代码
