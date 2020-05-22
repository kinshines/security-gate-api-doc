====================
闸机程序更新接口
====================

场景描述
----------
通过此接口查询闸机程序是否需要更新
查询到新版本后，闸机下载后覆盖重启

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP GET**  /api/config/upgrade?version={version}&devicecode={devicecode}

参数 **{devicecode}** 指定闸机编号
参数 **{version}** 指定当前版本号

请求URL示例
----------------------------
**HTTP GET**  /api/config/upgrade?version=1.0.2&devicecode=D05

.. include:: _include/release_response.rst
