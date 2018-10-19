.. security-gate-api documentation master file, created by
   sphinx-quickstart on Wed Oct 17 14:23:25 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

自助安检闸机服务与安检信息系统接口文档
=============================================

概述
>>>>>>>>>
在预安检和自助安检的业务场景中，旅客持有效证件或登机牌，经闸机扫描后，
闸机服务提取旅客证件信息或登机牌信息，发送至安检信息系统，由安检信息系统判定旅客可否通行，
返回指令给闸机服务，闸机服务据此展示给旅客相关信息并做出相应动作后反馈至安检信息系统

此Web服务接口由安检信息系统通过Web API提供，支持客户端基于HTTP协议请求调用，推荐JSON作为数据传输格式

目录
>>>>>>>>>

.. toctree::
   :maxdepth: 2
   
   pre_security
   pre_security_feedback
   self_security_first
   self_security_second
   self_security_feedback
   emergency
