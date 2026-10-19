# 贡献记录

> 社区改动收进本仓库时记一笔：谁、哪个 PR、收了什么、没收什么。协议细节留在专题文档。

## 2026-10-19

- **dotisland**（[#13](https://github.com/evren-oct/vigil-watt/pull/13)）：纳入 HECATE G5M Pro（`35BB:D00B`）只读电量插件，以及拔出设备后上报离线。认领收窄到 VID、PID 和 usage；迈从插件排除 `0x35BB`；探测窗口内没有任何报文则不认领。未纳入 [#14](https://github.com/evren-oct/vigil-watt/pull/14) 的按显示名去重。电量帧为本贡献者真机声明，本机未复测。
- **Baron77777**（[#16](https://github.com/evren-oct/vigil-watt/pull/16)）：纳入 AULA F99 Pro 与 DELUX M900 Pro 插件。AULA 只保留会话帧 `13 05 01`，不进 15 秒发现，默认关。DELUX 保持只读，但本机未扫到 `1D57`，默认关。未纳入删除离线、只显示在线、同源合并和电量条对齐。帧样本为本贡献者真机声明，本机未复测。
- **luze258**（[#15](https://github.com/evren-oct/vigil-watt/pull/15)）：这一笔只纳入 DualSense 蓝牙只读电量。未纳入 GANSS、MCHOSE V9 Pro，也未纳入 BLE 大改和按名字去重。电量档位为本贡献者声明，本机未复测。
