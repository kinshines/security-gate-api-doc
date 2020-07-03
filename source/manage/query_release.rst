====================
手持PAD程序更新接口
====================

场景描述
----------
通过此接口查询手持PAD程序是否需要更新

面向客户端
::::::::::::::::::::
手持PAD

请求URL
---------------------
**HTTP GET**  /api/config/release?version={version}

参数 **{version}** 指定当前版本号

请求URL示例
----------------------------
**HTTP GET**  /api/config/release?version=1.0.2

.. include:: ../_include/release_response.rst
