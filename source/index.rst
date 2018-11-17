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
返回指令给闸机服务，闸机服务据此展示给旅客相关信息并做出相应动作后反馈至安检信息系统。

安检信息系统同时对管理后台及移动端提供闸机的状态查询及控制接口，管理后台及移动端通过接口控制
闸机的工作模式及闸机动作，并实时查询闸机当前状态。

此Web服务接口由安检信息系统通过Web API提供，支持客户端基于HTTP协议请求调用，推荐JSON作为数据传输格式。

目录
>>>>>>>>>

.. toctree::
   :maxdepth: 2
   
   pre_security
   pre_security_feedback
   self_security_first
   self_security_second
   self_security_feedback
   push_emergency
   push_turnstile_status
   set_powermode
   set_powermode_feedback
   set_workmode
   set_workmode_feedback
   set_emergency
   set_emergency_feedback
   set_alert
   set_alert_feedback
   set_action
   set_action_open_feedback
   set_action_close_feedback
   query_status
   query_status_feedback
   query_devices
