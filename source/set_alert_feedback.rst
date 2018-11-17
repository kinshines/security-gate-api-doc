============================
控制闸机门关闭异步反馈
============================

场景描述
----------
发送 `控制闸机报警的指令 <set_alert_feedback.html>`_ 后，通过此接口异步反馈闸机的动作状态，

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/alert

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "data":"int", //报警状态, 1:正在报警;0:停止报警
        "execute":"string" //执行结果说明
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "data":1,
        "execute":"OK"
    }

.. include:: _include/gate_feedback_response.rst
