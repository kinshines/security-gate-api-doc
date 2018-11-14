====================
查询闸机列表
====================

场景描述
----------
通过此接口查询所有的闸机列表

请求URL
---------------------
**HTTP GET**  /api/gate/getalldevices?devicecode={devicecode}

参数 **{devicecode}** 可 **模糊** 查询闸机编号

请求URL示例
----------------------------
**HTTP GET**  /api/gate/getalldevices?devicecode=Z

响应体格式
-------------
::

    [
        {
            "id":"long", //闸机设备ID
            "deviceCode":"string", //闸机设备编号
            "gateType":"int", //闸机类型,1:单门; 2:双门
            "powerMode":"int", //开闭检状态,1:开检; 2:闭检
            "emergency":"int", //紧急状态,0:正常; 1:紧急
            "firstMode":"int", //一门工作模式,0:正常; 1:常开; 2:常闭
            "firstDirection":"int", //一门开门方向,0:反向; 1:正向
            "firstStatus":"int", //一门开关状态,0:关闭; 1:开启
            "secondMode":"int", //二门工作模式,0:正常; 1:常开; 2:常闭
            "secondDirection":"int", //二门开门方向,0:反向; 1:正向
            "secondStatus":"int", //二门开关状态,0:关闭; 1:开启
            "lastConnection":"datetime", //服务端与闸机的最近联系时间
            "online":"bool" //闸机是否在线
        }, //闸机状态
        ...
    ]

响应体示例
--------------
::

    [
        {
            "id": 1,
            "deviceCode": "Z001",
            "gateType": 2,
            "powerMode": 1,
            "emergency": 0,
            "firstMode": 0,
            "firstDirection": 1,
            "firstStatus": 1,
            "secondMode": 1
            "secondDirection": 0
            "secondStatus": 1
            "lastConnection": "2018-11-06T10:59:02",
            "online": true
        },
        {
            "Id": 2,
            "DeviceCode": "Z002",
            "GateType": 1,
            "PowerMode": 1,
            "Emergency": 0,
            "FirstMode": 0,
            "FirstDirection": 1,
            "FirstStatus": 1,
            "SecondMode": 1
            "SecondDirection": 0
            "SecondStatus": 1
            "LastConnection": "2018-11-06T10:56:02",
            "Online": true
        },
        ...
    ]


