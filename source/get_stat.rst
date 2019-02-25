====================
闸机过检人数统计
====================

场景描述
----------
通过此接口查询给定设备编号的闸机过检人数统计，按当日总计和分小时统计

面向客户端
::::::::::::::::::::
移动管理平台

请求URL
---------------------
**HTTP GET**  /api/gate/getstat?deviceCode={deviceCode}

参数 **{deviceCode}** 表示闸机设备编号

请求URL示例
----------------------------
**HTTP GET**  /api/gate/getstat?deviceCode=Z001

响应体格式
-------------
::

    {
        "dayStat": {
            "total": "int",
            "pass": "int",
            "intercept": "int",
            "lock": "int"
        },
        "hourStat": [
            {
                "hour": "int",
                "pass": "int"
            }
        ]
    }

响应体示例
--------------
::

    {
        "dayStat": {
            "total":"645",
            "pass":"545",
            "intercept":"50",
            "lock":"50"
        },
        "hourStat":[
            {
                "hour":"6",
                "pass":"60" 
            },
            {
                "hour":"7",
                "pass":"55" 
            },
            ...
        ]
    }


