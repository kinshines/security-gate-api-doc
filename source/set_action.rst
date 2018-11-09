====================
控制闸机门打开和关闭
====================

场景描述
----------
通过此接口控制闸机门的打开和关闭

请求URL
---------------------
**HTTP POST**  /api/gate/action?number={number}

参数 **{number}** 可指定一门和二门，若设置为1，则一门动作；若设置为2，则二门动作

请求URL示例
----------------------------
**HTTP GET**  /api/gate/action?number=1

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "Id":"long", //闸机设备ID,若值不为0,根据此字段查询设备,若为0或为提供,则根据DeviceCode查询设备
        "DeviceCode":"string", //闸机设备编号
        "FirstDirection":"int", //一门开门方向,指定一门打开时需设置此项, 0:反向;1:正向
        "FirstStatus":"int", //一门动作, 0:关闭;1:打开
        "SecondDirection":"int", //二门开门方向, 指定二门打开时需设置此项, 0:反向;1:正向
        "SecondStatus":"int" //二门动作, 0:关闭;1:打开
    }

请求体示例
----------------------------
::

    {
        "Id":1
        "DeviceCode":"Z001",
        "FirstDirection":1,
        "FirstStatus":1,
        "SecondDirection":0
        "SecondStatus":1
    }

.. include:: _include/gate_status_response.rst
