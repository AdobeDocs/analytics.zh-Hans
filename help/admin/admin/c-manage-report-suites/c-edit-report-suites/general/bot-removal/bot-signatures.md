---
title: 常见的机器人签名
description: 识别机器人的常见标识符。
feature: Bot Removal
role: Admin
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

---

# 常见的机器人签名

虽然识别数据集中的机器人因环境而异，但还是有下面这些共通的方法可识别机器人。

## 每次访问的页面查看次数很大

可拉取一个其中具有 IP 地址、页面查看次数和独特访客数的 Data Warehouse 报表。然后，在 Excel 中为每次访问的页面查看次数创建一个计算，并从最高到最低排序。机器人每次访问的页面查看次数一般都很大（数百至数千）。当转入真实流量时，就会发现次数急剧下降。

## 无反向链接

机器人一般不具备引用 URL。在分段时，可将这种情况过滤为 `Referring Domain equals Typed/Bookmarked`。

## 用户代理异常

机器人一般使用自定义用户代理，在“浏览器”维度中不为这些用户代理分类，或者这些用户代理显示为标准浏览器的 `unknown` 版本。未知的 Safari 和未知的 Opera 极有可能是机器人。

## Linux 或“未指定”的操作系统

我们无意贬低优秀的开源 Linux 操作系统，但机器人似乎喜欢将它设置为其操作系统。但是，请谨慎排除 Linux 用户产生的正当流量。机器人还喜欢不设置操作系统，而这种情况可归为 `Operating System &#x200B;equals Not Specified`。

## 页面查看次数 = 访问次数 = 独特访客数

这种情况尤其适用于用户代理报表。正如您可在下方的屏幕快照中所见，这些浏览器的“未知版本”的访问次数与独特访客数几乎相同（与页面查看次数也几乎相同）。通过为 `Single Page Visits equals Enabled` 或 `Hit Depth is less than 2` 构建[!UICONTROL 包括]容器，可在分段时发现这种情况。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bots-browsers-unknown.png)

## 访问次数为 1

机器人一般在每次执行时都获取一个新的访客 ID，因此仅产生一次访问，并且所有其流量都将由 1 次访问组成。

## 显示器分辨率较低

当代用户的显示器分辨率比多年之前高得多。机器人似乎很喜欢用以下分辨率进行点击：

* 1024 x 768
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* 未指定
* 1024 x 667

## 国家/地区与时区不匹配

您会注意到来源国家/地区与时区不匹配。例如，位置可能为美国，但时区可能为 GMT。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bots-country-time-zone.png)

## 未登录

用户在其访问期间从未登录，并且其用户标识 eVar 并非与以前的访问保持相同。虽然某些机器人可被设置为进行身份验证，但大多数没有那么智能。

## 访问中无 KPI

机器人一般不会将产品添加到购物车或结账。大多数时候它们不提交潜在客户表单或其他成功事件，但某些机器人确实会提交简单的 HTML 表单。

## 存在特定的查询字符串

有时，机器人通过点击异常的 URL 或不存在的 URL（如典型的 LAMP 或 Wordpress 管理页面）或追加特定的查询字符串，试图占满缓存或破坏网站。

## IP 地址来自分布式计算平台

可能滥用 Amazon Web Services 或 Google Cloud 等 Web 托管充当作机器人农场。这些 IP 地址很有可能是机器人：
* [Google Cloud](https://cloud.google.com/compute/)：以 `&#x200B;35.199` 或 `35.194&#x200B;` 开头的 IP 地址
