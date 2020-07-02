====================
查询单台闸机实时状态
====================

场景描述
----------
通过此接口查询闸机当前的状态，包括闸机的工作模式、开启状态，
注意此接口仅发送指令，闸机通过 `闸机状态反馈接口 <query_status_feedback.html>`_ 异步返回闸机的当前状态。

面向客户端
::::::::::::::::::::
安检管理后台和移动管理平台

请求URL
---------------------
**HTTP GET**  /api/gate/querystatus?devicecode={devicecode}

参数 **{devicecode}** 指定闸机编号

请求URL示例
----------------------------
**HTTP GET**  /api/gate/querystatus?devicecode=Z001

.. include:: ../_include/gate_command_response.rst
