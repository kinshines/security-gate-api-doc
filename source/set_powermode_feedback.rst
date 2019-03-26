============================
控制闸机开闭检状态异步反馈
============================

场景描述
----------
服务端发送 `控制闸机开闭检状态的指令 <set_powermode.html>`_ 后，闸机通过此接口异步反馈闸机的开闭检状态。

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/powermode

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "status":"int", //开检状态, 0:闭检;1:开检
        "execute":"string" //执行结果说明
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "status":1,
        "execute":"OK"
    }

.. include:: _include/gate_feedback_response.rst
