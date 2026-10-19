# 贡献记录

> 社区改动收进本仓库时记一笔：谁、哪个 PR、收了什么、没收什么。协议细节留在专题文档。

## 2026-10-19

- **dotisland**（[#13](https://github.com/evren-oct/vigil-watt/pull/13)）：纳入 HECATE G5M Pro（`35BB:D00B`）只读电量插件，以及拔出设备后上报离线。认领收窄到 VID、PID 和 usage；迈从插件排除 `0x35BB`；探测窗口内没有任何报文则不认领。未纳入 [#14](https://github.com/evren-oct/vigil-watt/pull/14) 的按显示名去重。电量帧为本贡献者真机声明，本机未复测。
