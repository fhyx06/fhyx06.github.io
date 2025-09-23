---
title: Scrcpy
date: 2025-09-22 16:27:04
tags:
---

Scrcpy: 开源的高性能工具，它允许你通过 USB 数据线或 WiFi 网络，在电脑上实时显示并控制你的安卓手机或平板设备

### 特性

- **轻量：** 原生体验，仅显示设备屏幕画面
- **性能：** 帧率 30~120fps (视设备性能而定)
- **画质：** 分辨率 1920×1080 或更高
- **低延迟：** 延迟<70 毫秒
- **启动快：** 约 1 秒显示首帧画面
- **无残留：** 安卓设备上不安装/不遗留任何文件
- **用户获益：** 无需账户、无广告、不联网也能用
- **自由开源：** 免费的自由开源软件 (FOSS)
- **更多：** 请查看[官方文档](https://github.com/Genymobile/scrcpy)（没有特殊手段会很慢）

### 前期准备

- **首先启用 USB 调试 (在手机上)：** 进入 <span style="color:#2A5C8B;">设置</span> -> <span style="color:#2A5C8B;">关于手机</span> -> 连续点击 <span style="color:#2A5C8B;">版本号</span> 7次，直到提示 “<span style="color:#2A5C8B;">您已处于开发者模式</span>”。接下来我们开启 <span style="color:#2A5C8B;">**USB** 调试</span>，连接电脑时，手机屏幕上可能会弹出“<span style="color:#2A5C8B;">允许USB调试吗？</span>”的授权框，勾选“ <span style="color:#2A5C8B;">始终允许</span>”并确认。
- **安装 ADB 驱动（Windows）：** 官方 SDK Platform-Tools [下载链接](https://developer.android.com/tools/releases/platform-tools?hl=zh-cn) (包含 adb)
- **接下来需要获取Scrcpy到本地：** [这里是Github链接](https://github.com/Genymobile/scrcpy/releases)
- 选择对应系统下载便好！（接下来Windows举例）。
- 解压压缩包会发现<span style="color:#2A5C8B;">scrcpy.exe</span>，一会儿要用的。

### 基础使用 (USB 连接)
- **连接手机：** 用 USB 数据线将手机连接到电脑。确保手机 USB 连接模式为传输文件或仅充电（只要能触发 adb 连接即可）。
- **首次连接授权：** 手机弹出 “<span style="color:#2A5C8B;">允许USB调试吗？</span>” 时，勾选 “<span style="color:#2A5C8B;">始终允许</span>” 并点击 “<span style="color:#2A5C8B;">确定</span>” 。
- **scrcpy 启动！(大声)：** 双击运行解压后文件夹里面的 “<span style="color:#2A5C8B;">scrcpy.exe</span>”。
- 然后你的电脑上应该就会弹出手机画面窗口

### 进阶使用 (WiFi 连接)
- 手机和电脑必须连接<span style="color:#2A5C8B;">同一个 WiFi 网络</span>。
- 先用 USB 线连接手机和电脑。
- 在scrcpy目录上面的路径显示框中输入cmd，然后回车即可，届时会弹出“命令提示符”窗口。
- 用 USB 数据线将手机连接到电脑，届时在cmd窗口输入 “`.\scrcpy.exe --tcpip`” 后拔掉数据线即可。
- 后续便可以直接使用 “`.\scrcpy.exe -e`” 进行局域网连接。

### 一些其他命令
- `--video-bit-rate` 单独控制视频码率（影响画质）
- `--audio`		启用音频传输（实验性功能）
- `--bit-rate 4M`	设置画质码率（默认8M，可降低延迟）
- `--max-size 1024`	限制分辨率宽度（如1024像素）
- `--window-title` 	"标题"	自定义窗口标题
- `--turn-screen-off`	投屏时关闭手机屏幕
- `--no-audio  禁用音频传输`（节省资源）

例如：季沧海想要画面码率为30Mbps，音频码率为320Kbps，同时关闭手机屏幕，那么他可以使用`.\scrcpy.exe --video-bit-rate 30M --audio-bit-rate 320K --turn-screen-off` 命令。

