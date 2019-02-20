============================
控制闸机工作模式异步反馈
============================

场景描述
----------
服务端发送 `控制闸机工作模式的指令 <set_workmode.html>`_ 后，闸机通过此接口异步反馈闸机的工作模式。

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/workmode

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "firstType":"int", //一门工作模式, 0:正常;1:常开;2:常闭
        "secondType":"int", //二门工作模式, 0:正常;1:常开;2:常闭
        "execute":"string" //执行结果说明
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "firstType":1,
        "secondType":2,
        "execute":"OK"
    }

.. include:: _include/gate_feedback_response.rst
