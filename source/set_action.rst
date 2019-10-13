======================
控制闸机栅门打开和关闭
======================

场景描述
----------
通过此接口控制闸机门的打开和关闭，
注意此接口仅发送指令，闸机通过 `闸机强制打开反馈接口 <set_action_breakopen_feedback.html>`_ 
或 `闸机强制关闭反馈接口 <set_action_breakclose_feedback.html>`_ 
或 `闸机强制放行反馈接口 <set_action_breakclose_feedback.html>`_异步返回闸机的动作状态。

面向客户端
::::::::::::::::::::
安检管理后台和移动管理平台

请求URL
---------------------
**HTTP POST**  /api/gate/action

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "number","int",//闸机栅门,1:一门,2:二门
        "status":"int", //动作, 2:强制关闭;3:强制打开;4:强制开门通过后自动关门(仅在闸机锁人时有效)
        "direction":"int", //开门方向,指定开门动作时需设置此项, 0:反向;1:正向
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "number":1,
        "status":3,
        "direction":1
    }

.. include:: _include/gate_command_response.rst
