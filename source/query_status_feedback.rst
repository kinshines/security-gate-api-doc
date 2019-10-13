============================
查询单台闸机实时状态异步反馈
============================

场景描述
----------
服务端发送 `查询闸机当前的状态的指令 <query_status.html>`_ 后，闸机通过此接口异步反馈闸机的当前状态，
同时，该服务作为闸机心跳接口，闸机每隔60秒向服务端发送一次闸机当前状态。

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/status

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "powerMode":"int", //0:闭检,1:开检
        "emergency":"int", //0:正常,1:紧急
        "firstType":"int", //一门状态, 0:关闭,1:正向开放,2:反向开放
        "secondType":"int", //二门状态, 0:关闭,1:正向开放,2:反向开放
        "lockType":"int", // 锁定状态, 0:未锁定,1:人脸识别失败,2:布控
        "execute":"string" //执行结果说明
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "powerMode":1,
        "emergency":0,
        "firstType":1,
        "secondType":0,
        "lockType":1
        "execute":"OK"
    }

.. include:: _include/gate_feedback_response.rst
