============================
闸机更新程序下载异步反馈
============================

场景描述
----------
为实现闸机的程序自动更新，管理平台通过服务端发送 `控制闸机更新程序(20)的指令 <../control/query_command.html>`_  后，闸机 `查询更新<../control/query_upgrade.html> `
下载完成后，通过此接口异步反馈闸机更新的下载状态。

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/upgrade

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "version":"string" //版本号
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "version":"1.0.2"
    }

.. include:: ../_include/gate_feedback_response.rst
