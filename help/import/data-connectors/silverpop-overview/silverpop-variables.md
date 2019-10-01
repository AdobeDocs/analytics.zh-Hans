---
description: Silverpop的Data Connectors集成使用Analytics变量跟踪各种Silverpop指标。
seo-description: Silverpop的Data Connectors集成使用Analytics变量跟踪各种Silverpop指标。
seo-title: 分析集成变量
title: 分析集成变量
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop的Data Connectors集成使用Analytics变量跟踪各种Silverpop指标。

在确定要与Silverpop集成一起使用的事件和eVar后，使用Adobe Analytics Admin Console启用它们(请参阅 [报表包](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html))。

下表介绍了Silverpop集成所需的Analytics变量。

## 必需变量 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| event（数字） | 跳出次数 | 自动从Silverpop导入。 | “弹回次数”事件允许您查看由于传送问题而未发送给收件人的电子邮件数。 |
| event（数字） | 点击次数 | 自动从Silverpop导入。 | 通过“已点击”事件，您可以查看点击电子邮件的访客数。 |
| event（数字） | 打开 | 自动从Silverpop导入。 | 通过“已打开”活动，您可以查看打开电子邮件的访客数。 |
| event（数字） | 发送 | 自动从Silverpop导入。 | “发送”事件可让您查看已发送的电子邮件数。 |
| event（数字） | 取消订阅 | 自动从Silverpop导入。 | 通过取消订阅活动，您可以查看打开电子邮件但随后单击取消订阅链接以选择退出您组织的将来电子邮件的访客数量。 |
| eVar | Silverpop ID/访客ID | 通过自动收集方法或JavaScript插件从电子邮件链接中的查询参数收集。 | 唯一访客ID |
| eVar或s.campaign | 邮寄ID | 通过自动收集方法或JavaScript插件从电子邮件链接中的查询参数收集。 | 这通常存储在系列活动变量中。 |

## 可选变量 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| event（计数器） | 已下载文件 | 通过Analytics标记手动收集。 | 此活动用于标识在站点上下载文件的用户。 |
| event（计数器） | 表单开始 | 通过Analytics标记手动收集。 | “表单开始”用于标识开始但未完成表单的用户。 |
| event（计数器） | 表单已完成 | 通过Analytics标记手动收集。 | “表单已完成”用于识别开始但未完成表单的访客。 |
| eVar | Email Address | 通过Analytics标记手动收集。 | 电子邮件地址用于在注册、登录或收集电子邮件地址的其他页面上手动收集电子邮件地址。 此变量用于向已选择接收电子邮件但过去可能尚未通过电子邮件点击的用户重新营销。 |
| eVar | 下载的文件 | 通过Analytics标记手动收集。 | “下载的文件”标识访客下载的文件。 |
| eVar | 表单名称 | 通过Analytics标记手动收集。 | 表单名称标识放弃的访客表单。 |

