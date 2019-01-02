======================
控制闸机栅门打开和关闭
======================

场景描述
----------
通过此接口控制闸机门的打开和关闭，
注意此接口仅发送指令，闸机通过 `闸机打开反馈接口 <set_action_open_feedback.html>`_ 或 `闸机关闭反馈接口 <set_action_close_feedback.html>`_ 异步返回闸机的动作状态。

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
        "id":"long", //闸机设备ID,若值不为0,根据此字段查询设备,若为0或未提供,则根据DeviceCode查询设备
        "deviceCode":"string", //闸机设备编号
        "number","int",//闸机栅门,1:一门,2:二门
        "direction":"int", //开门方向,指定一门打开时需设置此项, 0:反向;1:正向
        "status":"int", //动作, 0:关闭;1:打开
    }

请求体示例
----------------------------
::

    {
        "id":1
        "deviceCode":"Z001",
        "number":0
        "direction":1,
        "status":1
    }

.. include:: _include/gate_command_response.rst
