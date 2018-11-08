====================
控制闸机开检和闭检
====================

场景描述
----------
通过此接口控制闸机开检和闭检

请求URL
---------------------
**HTTP POST**  /api/gate/setpowermode

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "Id":"long", //闸机设备ID,优先根据此字段查询,若为0,则根据DeviceCode查询
        "DeviceCode":"string", //闸机设备编号
        "PowerMode":"int" //模式, 1:开检;2:闭检
    }

请求体示例
----------------------------
::

    {
        "Id":1
        "DeviceCode":"Z001",
        "PowerMode":1
    }

.. include:: _include/gate_status_response.rst
