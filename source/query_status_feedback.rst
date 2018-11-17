============================
查询单台闸机实时状态异步反馈
============================

场景描述
----------
服务端发送 `查询闸机当前的状态的指令 <query_status.html>`_ 后，闸机通过此接口异步反馈闸机的当前状态，
同时，该服务作为闸机心跳接口，闸机每隔60秒向服务端发送一次闸机当前状态。

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/status

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "firstHandleType":"int", //一门工作模式, 0:正常;1:常开;2:常闭
        "secondHandleType":"int", //二门工作模式,指, 0:正常;1:常开;2:常闭
        "firstType":"string", //一门状态, 10:正向开门,11:反向开门,00:关门
        "secondType":"string", //二门状态, 10:正向开门,11:反向开门,00:关门
        "execute":"string" //执行结果说明
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "firstHandleType":0,
        "secondHandleType":0,
        "firstType":"10",
        "secondType":"11",
        "execute":"OK"
    }

.. include:: _include/gate_feedback_response.rst
