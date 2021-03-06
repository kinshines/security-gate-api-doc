==================================
控制闸机门强制放行动作异步反馈
==================================

场景描述
----------
管理平台通过服务端发送 `控制闸机门强制放行的指令 <../manage/set_action.html>`_ 后，闸机通过此接口异步反馈闸机的动作状态。

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP POST**  /api/gatefeedback/forcepass

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "handleType":"int", //一门或二门, 1:一门;2:二门
        "direction":"int", //开门方向, 0:反向;1:正向
        "execute":"string" //执行结果说明
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "handleType":1,
        "direction":0,
        "execute":"OK"
    }

.. include:: ../_include/gate_feedback_response.rst
