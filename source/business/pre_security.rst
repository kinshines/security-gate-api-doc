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

.. include:: ../_include/idcard_request.rst

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

.. include:: ../_include/security_response.rst

响应值说明
::::::::::::::::::::::::::::

gateAction值说明
 - 在安检闸机第二道门开门请求响应中，有效值为0,1
 - 当gateAction为0时，闸机不予放行，并在一屏显示拦截原因
 - 当gateAction为1时，闸机开门放行，旅客进入后，栅门自动关闭