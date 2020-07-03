====================
闸机控制按钮状态
====================

场景描述
----------
通过此接口查询给定设备编号闸机控制状态，便于显示相关的按钮及可用状态

面向客户端
::::::::::::::::::::
移动管理平台

请求URL
---------------------
**HTTP GET**  /api/gate/getcontrolstatus?deviceCode={deviceCode}

参数 **{deviceCode}** 表示闸机设备编号

请求URL示例
----------------------------
**HTTP GET**  /api/gate/getcontrolstatus?deviceCode=Z001

响应体格式
-------------
::

    {
        "gateType":"int", //闸机类型,1:单门; 2:双门
        "powerMode":"int", //开闭检状态,1:开检; 0:闭检
        "emergency":"int", //紧急状态,0:正常; 1:紧急
        "firstStatus":"int", //一门状态,0:关闭; 1:正向打开; 2:反向打开
        "secondStatus":"int", //二门状态,0:关闭; 1:正向打开;
        "powerEnable":"bool", //开启(关闭)通道按钮是否可用
        "emergencyEnable":"bool", //紧急状态按钮是否可用
        "firstEnable":"bool", //一门开启(关闭)按钮是否可用
        "secondEnable":"bool", //二门开启(关闭)按钮是否可用
        "reverseEnable":"bool" //反向开启(关闭)按钮是否可用
    }

响应体示例
--------------
::

    {
        "gateType":2,
        "powerMode":1,
        "emergency":0,
        "firstStatus":1,
        "secondStatus":1, 
        "powerEnable":false,
        "emergencyEnable":true,
        "firstEnable":false, 
        "secondEnable":false, 
        "reverseEnable":false
    }

手持PAD闸机控制按钮显示说明
----------------------------------------------------
**手持PAD闸机控制及过检统计界面设计5个控制按钮，分别为：**

1.开启(关闭)通道按钮

2.开启(关闭)一门按钮

3.开启(关闭)二门按钮

4.反向开(关)门按钮

5.紧急状态(取消紧急)按钮

**手持PAD根据服务端返回值，显示按钮作如下调整：**

gateType：1表示预安检闸机，显示1,2,4,5按钮，2表示安检闸机，显示1,2,3,5按钮

powerMode：1表示当前状态为开检，按钮1显示文字为：关闭通道；0表示当前状态为闭检，按钮1显示文字为：开启通道

emergency：1表示当前状态为紧急，按钮5显示文字为：取消紧急；0表示当前状态为正常，按钮5显示文字为：紧急状态

firstStatus：0表示第一道栅门当前的状态为关闭，按钮2显示文字为：开启一门，按钮4显示文字为：反向开门；
1表示正向开启，按钮2显示文字为：关闭一门；
2表示反向开启，按钮4显示文字为：反向关门；

secondStatus：0表示第二道栅门当前的状态为关闭，按钮3显示文字为：开启二门；
1表示正向开启，按钮3显示文字为：关闭二门；

同时，powerEnable、firstEnable、secondEnable、reverseEnable、emergencyEnable分别控制1,2,3,4,5是否可点击，
可点击时呈蓝色背景按钮，不可点击时呈灰色背景按钮