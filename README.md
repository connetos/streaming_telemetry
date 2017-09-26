# Streaming Telemetry
ConnetOS提供steaming telemtry的能力，能将设备的telemetry（配置、状态等数据）以push的方式推送到对应设备上。

ConnetOS的telemetry从收集模式上可以分为以下两种：

- Dail-in模式，client通过远程gRPC调用向ConnetOS交换机订阅telemetry。
- Dail-out模式，ConnetOS交换机上通过CLI或者其他如API方式配置导出telemetry。

ConnetOS的telemetry从收集的时间上可以分为以下三种：

- 单次订阅，相当于获取；
- 周期性订阅，设备以一定的周期推送对应的telemetry；
- 订阅更新，在对应的telemetry发生变化的时候才进行推送；

ConnetOS的telemetry包括设备的配置和状态数据，ConnetOS提供的telemetry完全包括交换机的所有配置信息。ConnetOS通过将配置信息保存在内部的数据库通过telemetry的订阅提供给客户查询。同时ConnetOS将设备的协议状态信息保存在内部数据库中通过telemetry的订阅提供客户查询。ConnetOS还支持设备的外设状态信息通过telemetry订阅提供查询。



