# autoware_runtime_monitor

For English please refer to [English](./README.md)

本工具用于显示 autoware_system_msgs/NodeStatus.

消息的定义参考 [autoware_system_msgs in rosindex](https://index.ros.org/p/autoware_system_msgs/github-autoware-ai-messages/#noetic)

## 说明

基本界面如下

![ui_design](doc/image/2021-08-05-14-47-46.png)

根据消息定义，诊断消息有 4 个等级: OK, WARN, ERROR, FATAL

如果一个诊断key在5s之内还不更新，会标记上 **STALE** 标签, 说明此诊断信息已经失效.

## 配置使用

依赖这两个包 [autoware_system_msgs](https://github.com/Autoware-AI/messages/tree/master/autoware_system_msgs) and [autoware_health_checker](https://github.com/Autoware-AI/common/tree/master/autoware_health_checker)

```sh
rosrun autoware_runtime_monitor autoware_runtime_monitor
```

**注意**: 订阅的主题只能是 `/node_status` 其类型是 `autoware_system_msgs::NodeStatus`.
