=========================
自助安检第二道门开门请求
=========================

场景描述
----------
旅客通过自助安检闸机第一道门后，闸机对旅客拍照进行人脸比对，
将比对结果发送至安检信息系统，安检信息系统判断比对结果并反馈闸机第二道门下一步的动作

请求URL
-------------------------
**HTTP POST**  /api/selfsecurity/facerecognition

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string",//设备编号
        "similarity":"double",//人脸识别相似度
        "facePhoto":"string",//拍摄人脸照片(含背景)Base64编码
        "faceConstractPhoto":"string",//人脸识别图像(仅人脸)Base64编码
        "lastResponseId":"long"//第一道门请求响应的流水号
    }

请求体示例
----------------------------
::

    {
        "deviceCode":"Z001",
        "similarity":0.98,
        "facePhoto":"LKHKKJGJHGBHKJDSH42153544FDJAFOIJOIA123……",
        "faceConstractPhoto":"ABSSDDADFDSFDSH42153544FDJAFOIJOIA123……",
        "lastResponseId":7809242345
    }

.. include:: _include/security_response.rst
