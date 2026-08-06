---
title: "如何申请第三方登录-【Github登录】"
published: 2026-03-22
description: "详细教程：在GitHub创建OAuth App获取Client ID和Client Secret，实现第三方GitHub登录。"
tags: [教程, GitHub, 网站]
category: "技术分享"
---

![如何申请第三方登录-【Github登录】-封面](https://blog.laughsky.cn/wp-content/uploads/2024/05/83_0.webp)

Github登录不像QQ互联需要审核，简单几个步骤就可以接入。

但Github国内的访问可能会出现问题，比较适合技术网站使用，毕竟技术宅都是有Github帐号的。

## 创建开发者应用

首先你得有一个Github的帐号，没有的话就注册一个吧。邮箱注册也很简单！

### 1. 登录Github后，点击进入设置（Settings）

![步骤1 - GitHub Settings](/images/posts/83_1.webp)

### 2. 进入开发配置（Developer settings）

![步骤2 - Developer settings](https://blog.laughsky.cn/wp-content/uploads/2024/05/83_2-1024x555.webp)

### 3. 创建OAuth Apps，填写一些必要的信息

![步骤3 - 创建OAuth App](https://blog.laughsky.cn/wp-content/uploads/2024/05/83_3-1024x451.webp)

![步骤3 - 填写OAuth App信息](https://blog.laughsky.cn/wp-content/uploads/2024/05/83_4-1024x518.webp)

### 4. 记录 `Client ID` 和 `Client Secret`

此处还可上传网站logo。

![步骤4 - Client ID 和 Client Secret](https://blog.laughsky.cn/wp-content/uploads/2024/05/83_5-1024x546.webp)

### 5. 将 `Client ID` 和 `Client Secret` 填写到主题设置

保存之后，就可以在前端看到Github的登录按钮了。

---

> © 版权声明：文章版权归作者所有，未经允许请勿转载。
