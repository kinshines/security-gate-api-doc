====================
查询单台闸机实时状态
====================

场景描述
----------
通过此接口查询闸机当前的状态，包括闸机的工作模式、开启状态

请求URL
---------------------
**HTTP GET**  /api/gate/querystatus?devicecode={devicecode}

参数 **{devicecode}** 指定闸机编号

请求URL示例
----------------------------
**HTTP GET**  /api/gate/querystatus?devicecode=Z001

.. include:: _include/gate_status_response.rst
