# 贡献记录

> 社区改动收进本仓库时记一笔：谁、哪个 PR、收了什么、没收什么。协议细节留在专题文档。
> **面向用户的名单在根目录 [CONTRIBUTORS.md](../../CONTRIBUTORS.md)**（只写"谁做了什么"）；本文只记收了什么、没收到什么、是否本机复测，两处不重复。

## 2026-10-19

- **dotisland**（[#13](https://github.com/evren-oct/vigil-watt/pull/13)）：纳入 HECATE G5M Pro（`35BB:D00B`）只读电量插件，以及拔出设备后上报离线。认领收窄到 VID、PID 和 usage；迈从插件排除 `0x35BB`；探测窗口内没有任何报文则不认领。未纳入 [#14](https://github.com/evren-oct/vigil-watt/pull/14) 的按显示名去重。电量帧为本贡献者真机声明，本机未复测。
- **Baron77777**（[#16](https://github.com/evren-oct/vigil-watt/pull/16)）：纳入 AULA F99 Pro 与 DELUX M900 Pro 插件。AULA 只保留会话帧 `13 05 01`，不进 15 秒发现，默认关。DELUX 保持只读，但本机未扫到 `1D57`，默认关。未纳入删除离线、只显示在线、同源合并和电量条对齐。帧样本为本贡献者真机声明，本机未复测。
- **luze258**（[#15](https://github.com/evren-oct/vigil-watt/pull/15)）：这一笔只纳入 DualSense 蓝牙只读电量。未纳入 GANSS、MCHOSE V9 Pro，也未纳入 BLE 大改和按名字去重。电量档位为本贡献者声明，本机未复测。
- **luze258 / #15（第二轮）**：只纳入 GANSS GS3104T-Pro 2.4G 插件（`GanssCodec` + `GanssPlugin` + 单测）。未纳入同提交的 MCHOSE V9 Pro、BLE 大改（`BleBatteryWatcher` / `WatcherProps` / `DeviceKindGuesser` / `DeviceSourceInfo` / `SettingsPage`）与 DualSense（已在前一轮另行纳入）。认领硬绑 `05AC:024F` + `&mi_03#` + `0xFF60/0x0061` + 33 字节，会写查询帧，默认关。帧样本为本贡献者真机声明，本机无该设备，未复测。
- **zi-ha**（[#17](https://github.com/evren-oct/vigil-watt/pull/17)）：纳入鼠标 V2（A7 V2 Pro `3837:100A`）与 G87 V2（`3837:201B`）支持，以及按协议区分键盘/鼠标图标的 `ResolveKind`。认领加了 `0x3837` / `0x41E4` 白名单，≥60 字节接口只走鼠标通道。型号识别用官方密码表。键盘链路本机（G87 V1）复测通过；鼠标链路为本贡献者真机验证，本机未复测。
- **luze258 / #15（第三轮）**：只纳入 MCHOSE V9 Pro 耳机（`MchoseV9ProCodec` + 单测）。**没有按贡献者的做法新开 `MchoseV9Pro` 插件键**——设置页是品牌级开关（`AGENTS.md` §9），同品牌必须一行，故并入现有 `MchosePlugin`，协议名 `headset-v9`，共用 `PluginEnabled["Mchose"]`。未沿用贡献者的 `MinValidPercent => 1`（基类已无该成员；口径同 GANSS：0 由协议层拒、1 由公共下界拒）。另加一条回显保护：整帧等于查询帧时丢弃，避免把主机写入的回显读成 1%。仍未纳入同提交的 BLE 大改与 DualSense（已在前两轮处理）。帧样本为本贡献者真机声明，本机无该设备，未复测。
