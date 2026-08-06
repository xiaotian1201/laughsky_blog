---
title: "使用adb安装或卸载手机系统应用"
published: 2026-05-03
description: "Android SDK Platform-Tools（ADB）的下载、安装、配置及常用命令大全，包括应用管理、文件操作、设备控制等。"
tags: [ADB, Android, 安卓]
category: "技术分享"
---

**Android SDK Platform-Tools**（ADB、fastboot 等工具），最简单的方式是直接从 Google 官方下载对应平台的压缩包，解压即可使用，不需要额外安装 Android Studio。

## 1. 下载地址（官方）

> 建议从 [Google 官方下载页面](https://developer.android.com/studio/releases/platform-tools) 获取，以保证是最新版本。

- Windows：[https://dl.google.com/android/repository/platform-tools-latest-windows.zip](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
- MacOS：[https://dl.google.com/android/repository/platform-tools-latest-darwin.zip](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip)
- Linux：[https://dl.google.com/android/repository/platform-tools-latest-linux.zip](https://dl.google.com/android/repository/platform-tools-latest-linux.zip)

## 2. 安装步骤

### 2.1 解压

把下载好的压缩包解压到一个目录，例如：

- Windows: `C:\platform-tools`
- macOS/Linux: `~/platform-tools`

### 2.2 配置环境变量（方便全局使用 `adb`）

**Windows：**

1. 右键 "此电脑" → 属性 → 高级系统设置 → 环境变量
2. 在系统变量里找到 `Path` → 编辑 → 添加 `C:\platform-tools`
3. 确认并重启命令行

**macOS/Linux：**

编辑 `~/.bashrc` 或 `~/.zshrc`，加上：

```bash
export PATH=$PATH:$HOME/platform-tools
```

然后执行 `source ~/.bashrc` 或 `source ~/.zshrc`。

### 2.3 验证安装

连接好设备（记得在手机里打开 **开发者选项 → USB调试**），执行：

```
adb version
adb devices
```

如果能看到版本号和设备列表，就说明安装成功。

## 3. adb命令参数

### 3.1 adb 基本命令

| 命令 | 说明 |
| --- | --- |
| `adb devices` | 列出已连接的设备 |
| `adb version` | 查看 adb 版本 |
| `adb kill-server` | 停止 adb 服务 |
| `adb start-server` | 启动 adb 服务 |
| `adb reconnect` | 重新连接所有设备 |

### 3.2 设备连接相关

| 命令 | 说明 |
| --- | --- |
| `adb connect <ip>:<port>` | 通过 TCP/IP 连接设备（如 `adb connect 192.168.1.100:5555`） |
| `adb disconnect <ip>:<port>` | 断开网络设备连接 |
| `adb -s <serial>` | 指定设备执行命令（多设备时必须用） |

### 3.3 应用管理

| 命令 | 说明 |
| --- | --- |
| `adb install app.apk` | 安装 APK |
| `adb install -r app.apk` | 重新安装（保留数据） |
| `adb install -d app.apk` | 允许降级安装 |
| `adb install -g app.apk` | 安装并自动授予权限 |
| `adb uninstall <包名>` | 卸载应用 |
| `adb uninstall -k <包名>` | 卸载但保留数据和缓存 |

### 3.4 文件操作

| 命令 | 说明 |
| --- | --- |
| `adb push <本地文件> <设备路径>` | 复制文件到设备 |
| `adb pull <设备文件> <本地路径>` | 从设备复制文件 |
| `adb shell ls /sdcard/` | 列出设备文件目录 |

### 3.5 调试 & Shell

| 命令 | 说明 |
| --- | --- |
| `adb shell` | 进入设备 shell |
| `adb shell <命令>` | 执行单条命令，例如 `adb shell ls /sdcard/` |
| `adb logcat` | 查看系统日志 |
| `adb logcat -s <tag>` | 查看指定 tag 日志 |
| `adb bugreport` | 导出完整系统调试报告 |

### 3.6 设备控制

| 命令 | 说明 |
| --- | --- |
| `adb reboot` | 重启设备 |
| `adb reboot bootloader` | 重启到 bootloader |
| `adb reboot recovery` | 重启到 recovery |
| `adb root` | 以 root 模式重启 adb（设备需支持） |
| `adb remount` | 重新挂载系统分区为可写（需 root） |
| `adb tcpip 5555` | 开启 adb TCP/IP 连接模式，端口 5555 |

### 3.7 端口转发 & 调试

| 命令 | 说明 |
| --- | --- |
| `adb forward tcp:<本地端口> tcp:<设备端口>` | 本地端口转发到设备 |
| `adb reverse tcp:<设备端口> tcp:<本地端口>` | 设备端口转发到本地 |
| `adb shell am start -n <包名>/<Activity>` | 启动应用 |
| `adb shell pm list packages` | 列出所有安装的包 |
| `adb shell pm clear <包名>` | 清除应用数据 |

### 3.8 常用组合示例

**1. adb服务：**

```bash
adb start-server          # 启动adb服务
adb -P 5555 start-server  # 启动adb服务指定端口
adb kill-server           # 停止adb服务
```

**2. 连接：**

```bash
adb connect ip:port       # 连接设备
adb devices               # 查看设备
adb disconnect ip:port    # 断开特定设备
adb disconnect            # 断开所有连接
```

**3. 安装/使用：**

```bash
adb install -r app.apk                # 安装或更新 APK
adb push config.json /sdcard/         # 复制文件到设备
adb shell pm list packages            # 查看安装的包
adb logcat | grep Activity            # 过滤日志
adb tcpip 5555                        # 开启无线调试
adb connect 192.168.1.100:5555        # 连接设备
```

---

> © 版权声明：文章版权归作者所有，未经允许请勿转载。
