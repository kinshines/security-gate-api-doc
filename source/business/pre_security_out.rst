======================
预安检闸机旅客外出请求
======================

场景描述
----------
旅客通过预安检区域后，因某些原因要外出预安检区，通过闸机反向扫描证件，闸机将扫描到的证件信息发送至安检信息系统，安检信息系统判断旅客信息并反馈闸机下一步的动作。

面向客户端
::::::::::::::::::::
闸机

扫描证件信息请求URL
-------------------------
**HTTP POST**  /api/presecurity/out

.. include:: ../_include/idcard_request.rst

响应体格式
-------------
::

    {
        "responseId":"long",//响应流水号,用于闸机动作后反馈状态时提供
        "gateAction":"int",//闸机动作,附说明
        "statusCode":"int",//状态码,附说明
        "description":"string",//状态描述
        "type":"string",//证件类型
        "id":"string",//证件号
        "name":"string",//姓名
        "flightDate":"string",//航班日期
        "flightNo":"string",//航班号
        "departure":"string",//始发站
        "destination":"string",//目的站
        "seatNo":"string",//座位号
        "boardNo":"string",//登机号
    }

gateAction闸机动作说明
::::::::::::::::::::::::::::::::::::::::::::::::::::::

==========    ===========
gateAction            说明
==========    ===========
0                            关闭
11                           反向开启
==========    ===========

statusCode状态码说明
::::::::::::::::::::::::::::::::::::::::::::::::::::::

==========    ====================
statusCode            说明
==========    ====================
200                        正常通行
450                        不允许外出
==========    ====================

响应体示例
--------------
::

    {
        "responseId":7976321,
        "gateAction":11,
        "statusCode":200,
        "description":"正常通行",
        "type":"NI",
        "id":"110101197608056896",
        "name":"张三",
        "flightDate":"2018-10-10",
        "flightNo":"CA1234",
        "departure":"TAO",
        "destination":"CAN",
        "seatNo":"SN37A",
        "boardNo":"123"
    }