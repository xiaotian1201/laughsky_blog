---
title: "如何申请第三方登录-【QQ登录】"
published: 2025-12-15
description: "详细教程：在QQ互联平台申请QQ登录，包括已备案和未备案域名的完整申请流程。"
tags: [教程, QQ登录]
category: "技术分享"
---

![如何申请第三方登录-【QQ登录】-封面](/images/posts/81_0.webp)

QQ登录是非常常见的第三方登录，使用方便，申请比较简单，本篇教程将详细的教你如何申请 QQ登录。

## 申请步骤

首先在[QQ互联平台](https://connect.qq.com/)登录你的QQ，注册成为QQ互联平台开发者，点击应用管理。

![步骤 - 应用管理](/images/posts/81_1-1024x529.webp)

然后选择创建应用->创建网站应用。

![步骤 - 创建网站应用](/images/posts/81_2-1024x500.webp)

填写好相关资料->提交。

![步骤 - 填写资料](/images/posts/81_3-1024x566.webp)

接下来就是网站信息，需要准确的填写：

### 已备案域名

直接填写相关信息。

![步骤 - 已备案域名填写](/images/posts/81_4-1024x573.webp)

### 未备案域名

若服务器不在内地（不能备案），则资料填写之后，需要将以下东西发送邮件到 connect@qq.com。

填写以下表格（表格附在文章末尾）。

![步骤 - 未备案域名表格](/images/posts/81_5-1024x659.webp)

填写之后就可以发邮件了：

- 收件人填写：**connect@qq.com**
- 主题填写：**【国际域名接入】腾讯公司应用打通**
- 添加附件（表格和域名证书，证明文件），再将表格添加到正文，域名证书、证明文件也一同添加到正文，如下图：

![步骤 - 邮件发送示例](/images/posts/81_6-1024x605.webp)

接下来就是耐心等待审核，审核是否通过都会发邮件到自己邮箱。

## 获取ID和Key

审核通过之后，点击查看。

![获取ID和Key - 审核通过](/images/posts/81_7-1024x658.webp)

先确保应用接口中的 **登录** 和 **unionid** 均已获取。

然后记录 **`APP ID`** 和 **`APP Key`**（未备案域名的表格也是填写此处的 `APP ID` 和 `APP Key`）。

![获取ID和Key - APP ID 和 APP Key](/images/posts/81_8-1024x237.webp)

## 主题配置

本站使用的是[子比主题](https://www.zibll.com/?ref=691)，进入后台->主题设置->社交登录->QQ登录，开启QQ登陆，并填入 **`APP ID`** 和 **`APP Key`**。

![主题配置 - 子比主题QQ登录设置](/images/posts/81_9-1024x551.webp)

---

## 附件：国际域名接入QQ互联申请表

[下载](https://pan.laughsky.cn/d/Lanzou/International_Website_Application_Form_new.xlsx?sign=w9tzW4KJbWpny_fdT4Cv1x_tx0eXifpHasibHydUB6M=:0)

---

> © 版权声明：文章版权归作者所有，未经允许请勿转载。
