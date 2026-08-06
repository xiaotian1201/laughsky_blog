---
title: "ADB卸载小米预装系统应用（Hyper OS 3）"
published: 2026-02-17
description: "使用ADB命令卸载小米Hyper OS 3预装系统应用，包括广告服务、快应用、小爱同学、小米互联、游戏加速等全家桶应用。"
tags: [ADB, 小米, HyperOS]
category: "技术分享"
---

## 推荐卸载

> 小米广告与快应用跳转的含金量懂的都懂。

```bash
adb shell pm uninstall --user 0 com.miui.analytics           # Analytics——后台上传数据耗电
adb shell pm uninstall --user 0 com.miui.systemAdSolution    # 小米内置广告服务
adb shell pm uninstall --user 0 com.miui.hybrid              # 快应用服务框架——网页链接调用服务
adb shell pm uninstall --user 0 com.miui.daemon              # 系统质量服务
adb shell pm uninstall --user 0 com.miui.misightservice      # 系统质量监测
```

## 选择性卸载

```bash
adb shell pm uninstall --user 0 com.xiaomi.joyose                        # Joyose——神秘云控之一（也有说这个是温控的，卸载后可能导致部分游戏性能调整功能无法使用）
adb shell pm uninstall --user 0 com.sohu.inputmethod.sogou.xiaomi         # 小米定制版搜狗输入法
adb shell pm uninstall --user 0 com.android.browser                       # 小米浏览器
adb shell pm uninstall --user 0 com.miui.thirdappassistant                # 智能应用助手/第三方应用异常分析——明明APP运行得好好的，硬是给你弹"应用程序已崩溃"
adb shell pm uninstall --user 0 com.miui.video                            # 小米视频
adb shell pm uninstall --user 0 com.miui.player                           # 音乐
adb shell pm uninstall --user 0 com.android.quicksearchbox                # 搜索，桌面的那个搜索框
adb shell pm uninstall --user 0 com.miui.backup                           # 备份
adb shell pm uninstall --user 0 com.miui.accessibility                    # 小米闻声-小米无障碍
adb shell pm uninstall --user 0 com.miui.touchassistant                   # 悬浮球
adb shell pm uninstall --user 0 com.miui.greenguard                       # 家人守护
adb shell pm uninstall --user 0 com.miui.bugreport                        # 用户反馈
adb shell pm uninstall --user 0 com.xiaomi.ab                             # 售后支持
adb shell pm uninstall --user 0 com.miui.miservice                        # 服务与反馈
```

### 1. 小爱全家桶

> 后台耗电大户，尤其是开启语音唤醒后，但某些情况下又很有用。

```bash
adb shell pm uninstall --user 0 com.miui.voiceassist          # 小爱同学/超级小爱
adb shell pm uninstall --user 0 com.xiaomi.aicr               # 小米澎湃AI引擎-设置景深壁纸需要用到
adb shell pm uninstall --user 0 com.miui.voicetrigger         # 语音唤醒
adb shell pm uninstall --user 0 com.mediatek.voicecommand     # 语音控制-联发科处理器才有
adb shell pm uninstall --user 0 com.xiaomi.aireco             # 小爱建议
adb shell pm uninstall --user 0 com.xiaomi.aiasst.service     # AI通话/小爱通话
adb shell pm uninstall --user 0 com.xiaomi.aiasst.vision      # 翻译
```

### 2. 小米互联全家桶

> 后台耗电，但某些情况下又很有用。

```bash
adb shell pm uninstall --user 0 com.xiaomi.mirror             # 跨屏协同服务/MIUI+ Beta版
adb shell pm uninstall --user 0 com.xiaomi.mi_connect_service # 小米互联通信服务
adb shell pm uninstall --user 0 com.milink.service            # 互联互通服务/小米妙享中心
adb shell pm uninstall --user 0 com.xiaomi.hyperconmm         # Hyper Comm——跨设备高速互联框架
adb shell pm uninstall --user 0 com.miui.mishare.connectivity # 小米互传
adb shell pm uninstall --user 0 com.miui.phrase               # 剪贴板与常用语/常用语-小米云剪贴板
```

### 3. 传送门

> 超级小爱的识屏已经超越了它……

```bash
adb shell pm uninstall --user 0 com.miui.contentextension     # 传送门
```

### 4. 游戏加速服务

> 核心组件在手机管家里，卸了照样弹窗。

```bash
adb shell pm uninstall --user 0 com.xiaomi.gamecenter             # 游戏中心
adb shell pm uninstall --user 0 com.xiaomi.gamecenter.sdk.service # 游戏服务
adb shell pm uninstall --user 0 com.xiaomi.migameservice          # 游戏高能时刻
adb shell pm uninstall --user 0 com.miui.vpnsdkmanager            # MiuiVpnSdkManager-小米游戏加速的VPN服务
adb shell pm uninstall --user 0 com.xiaomi.macro                  # 自动连招
adb shell pm uninstall --user 0 com.xiaomi.barrage                # 弹幕通知
```

### 5. 下载管理组件

> 小米手机内置的精简版迅雷下载。

```bash
adb shell pm uninstall --user 0 com.android.providers.downloads.ui   # 下载管理
adb shell pm uninstall --user 0 com.android.providers.downloads      # 下载管理程序
```

### 6. 小米支付全家桶

> 小米智能卡这2个app涉及NFC复制门禁卡功能，按需保留。

```bash
adb shell pm uninstall --user 0 com.mipay.wallet                # 小米钱包
adb shell pm uninstall --user 0 com.unionpay.tsmservice.mi      # 银联可信服务安全组件小米版本
adb shell pm uninstall --user 0 com.miui.nextpay                # 小米支付
adb shell pm uninstall --user 0 org.mipay.android.manager       # Mipayservice
adb shell pm uninstall --user 0 com.xiaomi.payment              # 米币支付
adb shell pm uninstall --user 0 com.miui.tsmclient              # 小米智能卡
adb shell pm uninstall --user 0 com.miui.nextpay                # 小米智能卡网页组件
```

### 7. 小米人车家体系

```bash
adb shell pm uninstall --user 0 com.xiaomi.mis                  # 小米汽车互联服务（某些系统预装）
adb shell pm uninstall --user 0 com.miui.carlink                # CarWith
adb shell pm uninstall --user 0 com.xiaomi.digitalkey           # 小米数字钥匙框架
```

### 8. 小米云

```bash
adb shell pm uninstall --user 0 com.miui.cloudbackup            # 小米云备份
adb shell pm uninstall --user 0 com.miui.cloudservice           # 小米云服务
adb shell pm uninstall --user 0 com.miui.micloudsync            # MiCloudSync
adb shell pm uninstall --user 0 com.xiaomi.micloud.sdk          # 与相册云备份相关
```

### 9. 小米SIM卡

```bash
adb shell pm uninstall --user 0 com.xiaomi.smactivate.service   # 小米SIM卡激活服务
adb shell pm uninstall --user 0 com.miui.vsimcore               # MconnService——小米的虚拟SIM卡服务
adb shell pm uninstall --user 0 com.xiaomi.registration         # 运营商服务——卸载后影响未知
```

### 10. 小米安全管家组件

> ⚠️ 谨慎卸载，仅测试了卸后不卡米。有评论表示卸了似乎会影响QQ和微信使用，暂未实测。

```bash
adb shell pm uninstall --user 0 com.miui.securitymanager        # 手机管家——以下内容的快捷入口
adb shell pm uninstall --user 0 com.miui.securitycenter         # 安全服务——自启管理、自动任务、应用锁、SIM卡安全保护、省电模式、焕新存储
adb shell pm uninstall --user 0 com.miui.securitycore           # 系统功能组件——手机分身、应用双开、快捷手势、企业模式、维修模式、自由窗口、气泡通知
adb shell pm uninstall --user 0 com.miui.guardprovider          # 系统安全组件——病毒扫描引擎
adb shell pm uninstall --user 0 com.miui.securityadd            # 系统服务组件——儿童空间、红包助手战绩、迅游服务、游戏加速、地震预警
```

### 11. 支付组件

```bash
adb shell pm uninstall --user 0 com.tencent.soter.soterserver   # SoterService——为微信支付提供生物识别认证功能
adb shell pm uninstall --user 0 org.ifaa.aidl.manager           # IfaaService——为支付宝提供生物识别认证功能
adb shell pm uninstall --user 0 com.fido.asm                    # MI FIDO——与指纹支付功能相关
```

### 12. 后台分析组件

```bash
adb shell pm uninstall --user 0 com.miui.analytics                  # Analytics
adb shell pm uninstall --user 0 com.xiaomi.security.onetrack        # SecurityOnetrackService——配合MIUI analytics上传数据
adb shell pm uninstall --user 0 com.xiaomi.aon                      # 收集用户在线情况、追踪设备位置、面部识别情况
adb shell pm uninstall --user 0 com.xiaomi.touchservice             # 配合MIUI analytics，提供屏幕触摸轨迹
adb shell pm uninstall --user 0 com.miui.wmsvc                      # WMService——获取谷歌广告ID并发送给MIUI analytics
adb shell pm uninstall --user 0 com.xiaomi.metoknlp                 # 网络位置服务——仅在国内系统存在
adb shell pm uninstall --user 0 com.xiaomi.location.fused           # 融合位置服务——包含国内地理信息、广告、分析功能
adb shell pm uninstall --user 0 com.qualcomm.location               # LocationServices——定期向高通服务器发送设备信息
adb shell pm uninstall --user 0 com.qti.com                         # QCC——高通骁龙处理器特有，后台收集日志
adb shell pm uninstall --user 0 com.android.traceur                 # 系统跟踪——记录短时间内的系统活动
```

## 风险性卸载

> ⚠️ 亲测不卡米，但其他机型其他系统就说不定了。

```bash
adb shell pm uninstall --user 0 com.xiaomi.finddevice           # 查找——不可冻结，Hyper OS 3 卸载后不卡米
adb shell pm uninstall --user 0 com.miui.findmy                 # 查找设备——可冻结，Hyper OS 3 卸载后不卡米
adb shell pm uninstall --user 0 com.xiaomi.market               # 应用商店——经常自启后台运行且无法限制
adb shell pm uninstall --user 0 com.android.updater             # 系统更新——不可冻结，Hyper OS 3卸载后不卡米
```

> ❌ 以下为亲测卡米应用：

- `com.android.permissioncontroller` —— 权限管理器，卸了卡米
- `com.miui.packageinstaller` —— 应用包管理组件，卸了卡米
- `android.ext.services` —— Android Services Library，卸了卡米

## 不建议卸载

- `com.miui.misound` —— 音质音效，卸载了就没有小米调音和杜比全景声了
- `com.android.statementservice` —— Intent Filter Verification Service，决定哪些App可以免弹窗直接打开http链接
- `com.miui.dmregservice` —— RegService，卸载后会影响首次开机联网激活、无移动网络、支付失败等
- `org.codeaurora.ims` —— 高通AOSP代码里自带的IMS服务APK，卸载后无法使用4G/5G语音通话
- `com.android.phone` —— 电话服务，卸载后IMEI丢失，无法通过移动数据联网
- `com.lbe.security.miui` —— 权限管理服务，卸载后无法给应用授予权限
- `com.android.htmlviewer` —— HTML查看器，Hyper OS 3卸了虽然不卡米但无法操作，成为壁纸展示器
- `com.google.android.webview` —— Android System WebView，允许应用内直接显示网页内容
- `com.android.se` —— SecureElementApplication，为移动支付、公交、门禁、数字车钥匙等提供支持
- `com.mobiletools.systemhelper` —— 给渠道商/厂商提供静默装应用、写配置、读设备信息的能力
- `com.qualcomm.qti.services.systemhelper` —— System Helper Service，卸载后影响未知
- `org.codeaurora.ims` —— 提供网络通话支持（VoLTE / VoIP / WIFI通话）
- `com.qti.phone` —— 似乎与中国移动的SIM卡相关
- `com.android.captiveportallogin` —— 强制门户登录，连接公共WiFi需登录时弹出登陆页面
- `com.android.safetycenter.resources` —— 谷歌安全中心，卸不卸都无所谓
- `com.android.packageinstaller` —— 软件包安装服务，安卓原生的应用包安装组件
- `vendor.qti.frameworks.utils` —— 高通平台的系统级工具/库集合
- `vendor.qti.bluetooth.xpan` —— 高通平台的蓝牙扩展功能支持
- `com.qualcomm.qti.workloadclassifier` —— 高通平台的后台服务，按场景自动调频、调核、调温

### 额外优化命令

```bash
settings put system send_security_reports 0                           # 禁用安全报告
settings put secure send_action_app_error 0                           # 禁用错误报告
settings put global activity_starts_logging_enabled 0                 # 禁用活动日志
settings put system touch_prestart_opt_config "{featureDisable:false,bgExceptionInterceptDisable:false,touchDownPreStartBlackList:[disable_all_package]}"  # 禁用小米预加载
```

---

> **PS：**
> 1. 卸载联系人存储会发生：蓝牙不间断地自动开关
> 2. 网页链接调用服务——快应用总开关

---

> © 版权声明：文章版权归作者所有，未经允许请勿转载。
