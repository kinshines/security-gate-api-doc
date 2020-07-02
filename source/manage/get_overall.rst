====================
根据楼层获取闸机列表
====================

场景描述
----------
通过此接口查询给定楼层的闸机列表，列表中区分安检闸机和预安检闸机

面向客户端
::::::::::::::::::::
移动管理平台

请求URL
---------------------
**HTTP GET**  /api/gate/getoverall?floor={floor}

参数 **{floor}** 表示楼层

请求URL示例
----------------------------
**HTTP GET**  /api/gate/getoverall?floor=4

响应体格式
-------------
::

    {
        "preSecurity": [
            {
                "floor": "int", //所在楼层
                "region": "string", //所在安检区域
                "groupName": "string", //所属分组
                "deviceCode": "string", //设备编号
                "status": "string", //闸机运行状态
                "reason": "string" //状态原因
            },
        ],
        "selfSecurity": [
            {
                "floor": "int", //所在楼层
                "region": "string", //所在安检区域
                "groupName": "string", //所属分组
                "deviceCode": "string", //设备编号
                "status": "string", //闸机运行状态
                "reason": "string" //状态原因
            },
        ]
    }


响应体示例
--------------
::

    {
        "preSecurity": [
            {
                "floor": 4,
                "region": "国内",
                "groupName": "预安检闸机2组",
                "deviceCode": "Z001",
                "status": "停止工作",
                "reason": "通道关闭"
            },
            ...
        ],
        "selfSecurity": [
            {
                "floor": "3",
                "region": "国际",
                "groupName": "安检闸机3组",
                "deviceCode": "Z105",
                "status": "旅客拦截",
                "reason": "验证异常"
            },
            ...
        ]
    }


