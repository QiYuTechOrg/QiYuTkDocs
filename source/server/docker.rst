.. _server_docker:

.. meta::
   :description: 奇遇淘客服务器端 Docker 镜像
   :keywords: 奇遇淘客服务器Docker镜像, Docker 镜像, 奇遇淘客 Docker, 奇遇淘客服务器端


Docker 镜像
====================================

为了方便部署，我们使用了 Github Action 的自动集成自动发布 Docker 镜像包。


.. note::

    如果您需要部署奇遇淘客服务器端，请参考 :ref:`服务器端部署 <server_deploy>` 。

    这里的镜像仅供高级用户使用。


.. warning::

    如果您在线上部署，请不要使用 :code:`latest` 版本的 docker 镜像。


==========================
Docker Hub 官方镜像
==========================

`奇遇淘客 Docker 官方镜像地址 <https://hub.docker.com/r/qiyutech/tbk>`_

.. _tbk_docker_tag:

奇遇淘客 Docker Tags 信息 [0]_ 。

.. code-block:: bash

    docker pull qiyutech/tbk:${TAG}

.. warning::

    ${TAG} 应该使用 Docker Tag [0]_ 列表中的 tag 值替换

==============================
阿里云 Docker 镜像
==============================

阿里云镜像地址:

.. code-block:: bash

    docker pull registry.cn-hangzhou.aliyuncs.com/qiyutech/tbk:${TAG}

.. warning::

    ${TAG} 应该使用 Docker Tag [0]_ 列表中的 tag 值替换

.. note::

    中国的用户使用阿里云 Docker 镜像地址速度会比较快

=====================
ghcr 镜像
=====================

ghcr 镜像地址:


.. code-block:: bash

    docker pull ghcr.io/qiyutechdev/tbk:${TAG}

.. warning::

    ${TAG} 应该使用 :ref:`docker tag <tbk_docker_tag>` 列表中的 tag 值替换

====================
参考资料
====================

.. [0] `Docker Tags <https://hub.docker.com/r/qiyutech/tbk/tags>`_
