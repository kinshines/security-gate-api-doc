======================
预安检闸机开门请求
======================

场景描述
----------
旅客通过预安检闸机时，扫描证件或登机牌，闸机将扫描到的证件信息和登机牌信息发送至安检信息系统，安检信息系统判断旅客信息并反馈闸机下一步的动作。

面向客户端
::::::::::::::::::::
闸机

扫描证件信息请求URL
-------------------------
**HTTP POST**  /api/presecurity/id

扫描证件信息请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string",//设备编号
        "type":"string",//证件类型, NI:身份证;PP:护照;TP:港澳通行证;TW:台湾通行证; I:外国人永久居留身份证;ID:其他
        "id":"string",//证件号
        "name":"string",//姓名,身份证姓名,中文姓名
        "engName":"string",//英文名
        "validFromDate":"string",//发证日期
        "validToDate":"string",//有效日期
        "authority":"string",//发证机关
        "address":"string",//住址
        "birthday":"string",//出生日期
        "nation":"string",//国籍/民族,护照对应国籍;身份证对应民族
        "gender":"string",//性别,M:男;F:女;P:不区分性别
        "photo":"string"//头像Base64编码
    }

扫描证件信息请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "type":"NI",
        "id":"110101197608056896",
        "name":"张亿",
        "engName":"ZHANGYI",
        "validFromDate":"2012-01-01",
        "validToDate":"2020-01-01",
        "authority":"北京市公安局海淀分局",
        "address":"北京市海淀区门头沟95号",
        "birthday":"1976-08-05",
        "nation":"汉",
        "gender":"M",
        "photo":"ABSSDDADFDSFDSH42153544FDJAFOIJOIA123……"
    }

扫描登机牌信息请求URL
---------------------------
**HTTP POST**  /api/presecurity/boardpass

扫描登机牌信息请求体格式
-------------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string",//设备编号
        "boardPassNo":"string"//登机牌号码
    }

扫描登机牌信息请求体示例
------------------------------
::

    {
        "deviceCode":"Z001",
        "boardPassNo":"M1SURNAME/FIRSTNM ABCDEF TAOAAANH 9999O181C99999999 35D>5184 7181B1A 09999999999992A 0 NH XB FQTVNUMBER25FQTV Y*30699999K09 XBAASSR"
    }

.. include:: _include/security_response.rst
