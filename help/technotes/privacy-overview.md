---
description: 有关 Adobe Analytics 所收集数据和其他隐私注意事项的概述。
keywords: 隐私
title: 隐私概述
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 77e50dec593722855f30c517f63141e84f665519
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 96%

---

# 隐私概述

Adobe 建议您向网站访客提供易于查找且通俗易懂的信息，让访客可以选择禁止 Adobe 产品或服务收集其浏览信息。

访客可以进一步了解 Adobe 通常如何使用在 [Adobe 隐私中心](https://www.adobe.com/cn/privacy.html)收集的信息。这取决于贵组织是否披露 Adobe 产品和服务的用途，因为贵组织对于如何实施 Adobe 服务具有完全控制权。您负责创建自己的隐私政策，遵循您的隐私政策，您与 Adobe 之间的服务协议，以及所有适用法律。

## 数据收集细分 {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics 收集以下数据：

| 数据类型 | Adobe Analytics 是否收集此数据？ |
|---|---|
| 客户网站内的网页 URL | 是 |
| 网页的名称 | 是 |
| 页面逗留时间 | 是 |
| 时间 | 是 |
| 独立网站上的网页 URL | **否** |
| Cookie ID（随机生成） | 是 |
| 访问客户页面之前用户所在页面的 URL | 是 |
| 消费者单击客户页面链接时的搜索查询 | 是 |
| 浏览器类型 | 是 |
| 设备类型 | 是 |
| 操作系统 | 是 |
| ISP/连接速度 | 是 |
| 显示设置（例如屏幕大小和分辨率） | 是 |
| IP 地址（用于估算位置） | 是&#42; |
| 消费者在客户网站上的表格中提供的信息 | 是 |
| 消费者在社交网站上的表格中提供的信息 | **否** |
| 消费者是否点击了广告 | 是 |
| 消费者是否点击了网站上的链接、图像或文本 | 是 |
| 消费者是否下载了文件、图像等 | 是 |
| 消费者购买的项目 | 是 |
| 购物车中的剩余项目 | 是 |
| 社交网络信息（包括照片、用户 ID、年龄、性别和位置） | **否** |
| 用户在我们的服务范围之外提供的个人信息 | 是 |
| 广告促销成功率 | 是 |
| 产品信息，例如颜色、价格、样式、照片 | 是 |

&#42;除非 Adobe 客户选择移除 IP。

## 其他隐私注意事项 {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

| 地区/国家 | 注意事项 |
|--- |--- |
| 全球 | Adobe 强烈建议客户避免将个人可识别信息 (PII) 传递到 Adobe，特别是在 Analytics 不要求必须提供 PII 的情况下。 |
| 全球 | 在收集资料时，需要通知用户，并让用户做出选择。在加拿大、澳大利亚、欧盟（一些国家/地区可选择加入）以及拉美和亚太地区的许多国家/地区，这是法律规定。 |
| 全球 | 如果使用第一方 Cookie，Analytics 退出仅针对于某个客户；不能在 Adobe.com 上使用退出选项。 |
| 全球 | 第一方分析不在针对在线行为广告 (AdChoices) 的自律计划的范围之内。 |
| 全球 | 不应该合并跨设备数据，除非数据绑定到客户提供的标识符（例如哈希用户名）。 |
| 全球 | 对于客户将广告展示信息合并到 PII 可能存在相关限制。 |
| 欧洲 | 欧盟中的大多数国家/地区并不认为 Analytics Cookie 绝对必要。 |
| 欧洲 | Adobe 启用了设置 IP 模糊处理：对于欧洲、中东和非洲地区使用报告包集的所有客户，默认设置为“已启用 — IP 已删除 (x.x.x.x)”。通过此设置，在地理查询后 IP 地址将由值 (x.x.x.x) 完全取代，且不再可作为数据点使用。这个基本替换方法无法通过实施反向工程返回一个唯一的特定 IP 地址。客户或 Adobe 均无法访问该 IP 地址，该 IP 地址已经过不可逆转的匿名化处理。有关其他 IP 混淆设置的详细信息，请参阅管理员用户指南中的[常规帐户设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)。 |
| 全球 | 客户可以在 JavaScript 指标代码中将 Cookie 持续时间变量设置为“none”、“session”值，或其他以秒为单位的特定值。 |
| 欧洲 | Adobe 制定了新的“从设计着手保护隐私”设置，Adobe ClientCare 为 Adobe Analytics（以前称为 SiteCatalyst）发布版本 14.9 和 15.4 启用了此设置。启用这一新设置后，当 Adobe 收集 IP 地址时，该 IP 地址的最后八位字节（最后一部分）会立即被 0 值取代。在对 IP 地址进行任何处理之前，包括在对 IP 地址进行可选地理查询和 ISP 查询之前，会执行此匿名化操作。 |
| 德国 | 如果您尚未与 Adobe 就 Adobe Analytics 签订数据处理协议 (Data Processing Agreement)，则应与 Adobe 客户经理或客户成功经理取得联系，他们会与 Adobe 法律部合作，协助签订 DPA。 |

## EMEA数据中心位置 {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

以下EMEA数据中心当前托管Adobe Analytics数据：

| Adobe 名称 | 地址 | 设备类型（运营商） | 支持的解决方案组件 | 证书 |
|--- |--- |--- |--- |--- |
| LON5 | 3 Centro  Boundary Way Hemel Hempstead HP2 7SU UK | Colocation Facility(Gyron) | 多渠道分析， Digital Analytics | SSAE 16 |