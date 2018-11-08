响应体格式
-------------
::

    {
        "Success":"bool",//操作是否成功
        "Message":"string",//附加说明
        "Data":
        {
            "Id":"long",//闸机设备ID
            "DeviceCode":"string",//闸机设备编号
            "GateType":"int",//闸机类型,1:单门; 2:双门
            "PowerMode":"int",//开闭检状态,1:开检; 2:闭检
            "Emergency":"int",//紧急状态,0:正常; 1:紧急
            "FirstMode":"int",//一门工作模式,0:正常; 1:常开；2:常闭
            "FirstDirection":"int",//一门开门方向,0:反向; 1:正向
            "FirstStatus":"int",//一门开关状态,0:关闭; 1:开启
            "SecondMode":"int",//二门工作模式,0:正常; 1:常开；2:常闭
            "SecondDirection":"int",//二门开门方向,0:反向; 1:正向
            "SecondStatus":"int",//二门开关状态,0:关闭; 1:开启
            "LastConnection":"datetime",//服务端与闸机的最近联系时间
            "Online":"bool"//闸机是否在线
        }//闸机状态
    }

响应体示例
--------------
::

    {
        "Success":true
        "Message":"操作成功",
        "Data":
        {
            "Id": 1,
            "DeviceCode": "Z001",
            "GateType": 2,
            "PowerMode": 1,
            "Emergency": 0,
            "FirstMode": 1,
            "FirstDirection": 1,
            "FirstStatus": 1,
            "SecondMode": 1
            "SecondDirection": 0
            "SecondStatus": 0
            "LastConnection": "2018-11-06T10:59:02",
            "Online": true
        }
    }

