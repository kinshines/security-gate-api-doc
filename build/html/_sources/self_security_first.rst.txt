==========================
自助安检第一道门开门请求
==========================

场景描述
----------
旅客通过自助安检闸机时，扫描证件，闸机将扫描到的证件信息发送至安检信息系统，安检信息系统判断旅客信息并反馈闸机下一步的动作

请求URL
-------------------------
**HTTP POST**  /api/selfsecurity/id

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "DeviceCode":"string",//设备编号
        "Type":"string",//证件类型, NI:身份证;PP:护照;TP:港澳通行证;TW:台湾通行证; I:外国人永久居留身份证;ID:其他
        "Id":"string",//证件号
        "Name":"string",//姓名,身份证姓名,中文姓名
        "EngName":"string",//英文名
        "ValidFromDate":"string",//发证日期
        "ValidToDate":"string",//有效日期
        "Authority":"string",//发证机关
        "Address":"string",//住址
        "Birthday":"string",//出生日期
        "Nation":"string",//民族
        "Gender":"string",//性别,M:男;F:女;P:不区分性别
        "Photo":"string"//头像base64编码
    }

请求体示例
----------------------------
::

    {
        "DeviceCode":"Z001",
        "Type":"NI",
        "Id":"110101197608056896",
        "Name":"张亿",
        "EngName":"ZHANGYI",
        "ValidFromDate":"2012-01-01",
        "ValidToDate":"2020-01-01",
        "Authority":"北京市公安局海淀分局",
        "Address":"北京市海淀区门头沟95号",
        "Birthday":"1976-08-05",
        "Nation":"汉",
        "Gender":"M",
        "Photo":"ABSSDDADFDSFDSH42153544FDJAFOIJOIA123……"
    }

.. include:: /_include/security_response.rst