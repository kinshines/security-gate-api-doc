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
        "flightStatus":"string"//航班状态,ONR:前站起飞;ARR:本站到达;CKI:值机开始;CKO:值机截止;BOR:登机开始;TBR:过站登机;LBD:催促登机;POK:登机截止;DEP:起飞;DLY:延误;CAN:取消;RTN:返航;ALT:备降
    }

gateAction闸机动作说明
::::::::::::::::::::::::::::::::::::::::::::::::::::::

==========    ===========
gateAction            说明
==========    ===========
0                            关闭
1                            开启
2                            报警
3                            开启通过后报警
==========    ===========

statusCode状态码说明
::::::::::::::::::::::::::::::::::::::::::::::::::::::

==========    ====================
statusCode            说明
==========    ====================
200                        正常通行
201                        催促登机
202                        重复安检
400                        证件失效
401                        始发站有误
402                        航班日期有误
403                        值机删除
404                        尚未值机
405                        携带婴儿
406                        区域有误
409                        闸机设备未识别
410                        航班未找到
411                        航班延误
412                        航班取消
413                        航班起飞
414                        登机截止
415                        多张机票
421                        布控航班
422                        布控人员
423                        黑名单
430                        人脸比对失败
431                        人脸比对失败次数超过上限
440                        目的站未识别
441                        参数错误
==========    ====================

响应体示例
--------------
::

    {
        "responseId":7976321,
        "gateAction":0,
        "statusCode":413,
        "description":"航班已起飞，禁止通行",
        "type":"NI",
        "id":"110101197608056896",
        "name":"张三",
        "flightDate":"2018-10-10",
        "flightNo":"CA1234",
        "departure":"TAO",
        "destination":"CAN",
        "seatNo":"SN37A",
        "boardNo":"123",
        "flightStatus":"DEP"
    }
