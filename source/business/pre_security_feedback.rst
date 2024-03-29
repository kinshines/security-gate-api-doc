========================
预安检开门结果反馈
========================

场景描述
----------
在预安检闸机开门请求根据安检信息系统返回值做出动作后，须将闸机状态及拍摄的人脸照片反馈至安检信息系统。

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP POST**  /api/presecurity/feedback

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string", //闸机设备编号
        "status":"int", //闸机状态,附说明
        "lastResponseId":"long",  //上次开门请求的响应流水号
        "facePhoto":"string",  //拍摄人脸照片(含背景)Base64编码
        "faceConstractPhoto":"string"//人脸识别图像(仅人脸)Base64编码
    }

status闸机状态说明
::::::::::::::::::::::::::::::::::::::::::::::::::::::

==========    ==============================
status                    说明
==========    ==============================
1                            第一道门有尾随，尾随成功
2                            第一道门有尾随，未通过
3                            人员离开第一道门感应区
4                            第一道门正常通过且关门
5                            第一道门无旅客进入，超时关闭
10                          未捕获到人脸，门未开
==========    ==============================


请求体示例
--------------------------
::

    {
        "deviceCode":"Z001",
        "status":4,
        "lastResponseId":7976321,
        "facePhoto":"LKHKKJGJHGBHKJDSH42153544FDJAFOIJOIA123……",
        "faceConstractPhoto":"hrwubcasbckdjhasdlhagdlfhasldfh……"
    }

.. include:: ../_include/security_feedback_response.rst
