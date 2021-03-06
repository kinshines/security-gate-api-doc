====================
闸机程序更新接口
====================

场景描述
----------
为实现闸机的程序自动更新，管理平台通过服务端发送 `控制闸机更新程序(20)的指令 <../control/query_command.html>`_  后，闸机通过此接口查询是否需要更新
查询到新版本后，闸机下载后覆盖重启

面向客户端
::::::::::::::::::::
闸机

请求URL
---------------------
**HTTP GET**  /api/config/upgrade?devicecode={devicecode}

参数 **{devicecode}** 指定闸机编号

请求URL示例
----------------------------
**HTTP GET**  /api/config/upgrade?devicecode=D05

响应体格式
-------------
::

    {
        "user":"string", //ftp用户名
        "password":"string", //ftp登录密码
        "url":"string", //下载地址
        "changeLog":"string", //版本更新说明
        "version":"string" //版本号
    }

响应体示例
-------------
::

    {
        "user":"gateuser",
        "password":"!WH86tfpk",
        "url":"ftp://192.168.163.36/release/gatebuild.zip",
        "changeLog":"闸机控制功能优化",
        "version":"1.0.2"
    }
