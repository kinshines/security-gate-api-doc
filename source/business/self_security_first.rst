==========================
自助安检第一道门开门请求
==========================

场景描述
----------
旅客通过自助安检闸机时，扫描证件，闸机将扫描到的证件信息发送至安检信息系统，安检信息系统判断旅客信息并反馈闸机下一步的动作

面向客户端
::::::::::::::::::::
闸机

请求URL
-------------------------
**HTTP POST**  /api/selfsecurity/id

.. include:: ../_include/idcard_request.rst

.. include:: ../_include/security_response.rst

响应值说明
::::::::::::::::::::::::::::

gateAction值说明
 - 在安检闸机第一道门开门请求响应中，有效值为0,1,3
 - 当gateAction为0时，闸机一门不予放行，并在一屏显示拦截原因
 - 当gateAction为1时，闸机一门开门放行，旅客进入后，一门关闭，开启人脸比对，并进行二门请求
 - 当gateAction为3时，闸机一门开门放行，旅客进入后，一门关闭，但不再进行人脸比对和二门请求，进入锁定模式，并记录lockType的值作为锁定类型，用于心跳时上报

wait值说明
 - 仅在安检闸机第一道门开门响应中，该值有效，在其他的请求响应值中，为无效值 0
 - 闸机程序在收到第一道门开门响应后，开始倒计时，如wait=10，则倒计时10秒
 - 旅客进入一门，开始人脸比对，比对成功，正常通过二门，二门关闭，此过程倒计时不停止，若此过程耗时6秒，则倒计时剩余4秒
 - 此时一屏显示倒计时画面，提示后续旅客等待，从4秒钟开始倒计时，每秒刷新画面
 - 到倒计时为0时，一屏切换至欢迎页，后续旅客方可继续刷证过检
 - 若旅客在二门处的验证时间超过10秒，即当该旅客验证完毕后，倒计时剩余0秒，则后续旅客无需等待，一屏直接切换至欢迎页
