=========================
自助安检第二道门开门请求
=========================

场景描述
----------
旅客通过自助安检闸机第一道门后，闸机对旅客拍照进行人脸比对，
将比对结果发送至安检信息系统，安检信息系统判断比对结果并反馈闸机第二道门下一步的动作。

面向客户端
::::::::::::::::::::
闸机

请求URL
-------------------------
**HTTP POST**  /api/selfsecurity/facerecognition

请求体格式
----------------------------
请求体格式为JSON，字段名不区分大小写::

    {
        "deviceCode":"string",//设备编号
        "similarity":"double",//人脸识别相似度,对于超时未捕捉到画面的情形,该项传-1,Photo传空字符串
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

.. include:: ../_include/security_response.rst

响应值说明
::::::::::::::::::::::::::::

gateAction值说明
 - 在安检闸机第二道门开门请求响应中，有效值为0,1,2,6
 - 当gateAction为1时，闸机二门开门放行，旅客通过后，二门关闭，验证流程结束
 - 当gateAction为6时，闸机二门不予放行，且重新发起人脸比对请求
 - 当gateAction为0时，闸机二门不予放行，且不再发起人脸比对请求，进入锁定模式，
   并记录lockType的值作为锁定类型，用于心跳时上报
 - 当gateAction为2时，闸机二门不予放行，且不再发起人脸比对请求，进入锁定模式，
   并记录lockType的值作为锁定类型，用于心跳时上报，同时播放报警音长鸣，报警音直到工作人员介入处理后结束