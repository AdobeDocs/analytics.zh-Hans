---
description: Silverpop 的 Data Connectors 集成使用 Analytics 变量来跟踪不同的 Silverpop 量度。
title: Analytics 集成变量
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 集成变量{#analytics-integration-variables}

Silverpop 的 Data Connectors 集成使用 Analytics 变量来跟踪不同的 Silverpop 量度。

在确定要与 Silverpop 集成一起使用的事件和 eVar 后，使用 Adobe Analytics Admin Console 启用它们（请参阅[报表包](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/manage-report-suites/report-suites-admin.html)）。

下表描述了 Silverpop 集成所需的 Analytics 变量。

## 必需变量 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| 事件（数字） | 退回 | 自动从 Silverpop 导入。 | “退回”事件让您能够查看由于传输问题而未发送给收件人的电子邮件数量。 |
| 事件（数字） | 点击 | 自动从 Silverpop 导入。 | “已点击”事件让您能够查看点击了电子邮件的访客数量。 |
| 事件（数字） | 打开 | 自动从 Silverpop 导入。 | “已打开”事件让您能够查看打开了电子邮件的访客数量。 |
| 事件（数字） | 发送 | 自动从 Silverpop 导入。 | “已发送”事件让您能够查看已发送的电子邮件数量。 |
| 事件（数字） | 取消订阅 | 自动从 Silverpop 导入。 | “已取消订阅”事件让您能够查看以下访客的数量：打开了电子邮件，但随后单击“取消订阅”链接以选择退出接收贵组织今后的电子邮件。 |
| eVar | Silverpop ID/访客 ID | 通过自动收集方法或 JavaScript 插件，从电子邮件链接中的查询参数收集。 | 唯一的访客 ID |
| eVar 或 s.campaign | 邮件 ID | 通过自动收集方法或 JavaScript 插件，从电子邮件链接中的查询参数收集。 | 它通常存储在促销活动变量中。 |

## 可选变量 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| 事件（计数器） | 已下载文件 | 通过 Analytics 标记手动收集。 | 此事件用于标识已在网站上下载文件的用户。 |
| 事件（计数器） | 已开始表单 | 通过 Analytics 标记手动收集。 | “已开始表单”用于标识已开始填写但未完成表单的用户。 |
| 事件（计数器） | 已完成表单 | 通过 Analytics 标记手动收集。 | “已完成表单”用于标识已开始填写且已完成表单的访客。 |
| eVar | 电子邮件地址 | 通过 Analytics 标记手动收集。 | “电子邮件地址”用于在注册、登录或收集电子邮件地址的其他页面上手动收集电子邮件地址。此变量用于向已选择接收电子邮件，但过去可能尚未通过电子邮件点击的用户进行再营销。 |
| eVar | 下载的文件 | 通过 Analytics 标记手动收集。 | “下载的文件”用于标识访客下载的文件。 |
| eVar | 表单名称 | 通过 Analytics 标记手动收集。 | “表单名称”用于标识访客放弃的表单。 |

