---
description: Silverpop的数据连接器集成使用Analytics变量跟踪各种Silverpop指标。
seo-description: Silverpop的数据连接器集成使用Analytics变量跟踪各种Silverpop指标。
seo-title: 分析集成变量
title: 分析集成变量
uuid: aef3Caf-e24 e-4fe7-b4 d7-50ca0 f6703 b5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop的数据连接器集成使用Analytics变量跟踪各种Silverpop指标。

After identifying the Event and eVars to use with the Silverpop integration, use the Adobe Analytics Admin Console to enable them (see [Report Suites](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin)).

下表描述了Silverpop集成所需的Analytics变量。

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| event(数字) | 跳出次数 | 自动从Silverpop导入。 | “跳出次数”事件允许您查看由于交付问题而未发送给收件人的电子邮件数。 |
| event(数字) | 点击次数 | 自动从Silverpop导入。 | 单击“单击”事件可查看单击该电子邮件的访客的数量。 |
| event(数字) | 打开时间 | 自动从Silverpop导入。 | 打开的活动可让您查看打开电子邮件的访客的数量。 |
| event(数字) | 发送内容 | 自动从Silverpop导入。 | 发送事件可让您查看发送的电子邮件数。 |
| event(数字) | 退订 | 自动从Silverpop导入。 | 通过取消订阅活动，您可以查看打开电子邮件的访客数量，但单击取消订阅链接以退出单位以后的电子邮件消息。 |
| eVar | Silverpop ID/访问者ID | 通过自动收集方法或JavaScript插件从电子邮件链接的查询参数中收集。 | 唯一访问者ID |
| eVar或s. campaign | 邮寄ID | 通过自动收集方法或JavaScript插件从电子邮件链接的查询参数中收集。 | 这通常存储在营销活动变量中。 |

## 可选变量 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 变量类型 | 名称 | 填充方法 | 描述 |
|---|---|---|---|
| event(计数器) | 已下载文件 | 通过Analytics标记手动收集。 | 此事件用于识别下载站点上的文件的用户。 |
| event(计数器) | 表单开始 | 通过Analytics标记手动收集。 | “表单入门”用于标识开始表单但未完成表单的用户。 |
| event(计数器) | 填写表单 | 通过Analytics标记手动收集。 | 填写表单用于标识开始表单且未完成表单的访客。 |
| eVar | Email Address | 通过Analytics标记手动收集。 | 电子邮件地址用于手动收集在上收集电子邮件地址的注册、登录或其他页面上的电子邮件地址。此变量用于重新进入已选择接收电子邮件的用户，但过去可能还未点击过去的电子邮件。 |
| eVar | 下载的文件 | 通过Analytics标记手动收集。 | 下载的文件标识下载的访客的文件。 |
| eVar | 表单名称 | 通过Analytics标记手动收集。 | “表单名称”标识访客放弃的表单。 |

