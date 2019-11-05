---
description: 数据隐私中的隐私报表的变量。
seo-description: 数据隐私中的隐私报表的变量。
seo-title: 隐私报表变量
solution: Analytics
title: 隐私报表变量
topic: 管理工具
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# 隐私报表变量

要在管理隐私数据方面提供额外帮助，可以将一组保留变量与特定的上下文数据变量结合起来使用。这些隐私报表变量为在每次 Analytics 命中时捕获隐私状态提供了一个易于使用的框架。

## 变量

* 同意管理选择退出
   * 保留变量：列表 Prop
   * 类型：逗号分隔的字符串
   * 包含:
      * `contextData.['cm.ssf']=1` 显示为 SSF
      * `contextData.['opt.dmp']=N` 显示为 DMP
      * `contextData.['opt.sell']=N` 显示为 SELL

* 同意管理选择加入
   * 保留变量：列表 Prop
   * 类型：逗号分隔的字符串
   * 包含:
      * `contextData.['opt.dmp']=Y` 显示为 DMP
      * `contextData.['opt.sell']=Y` 显示为 SELL

## 报表

您可以通过 Analytics Admin Console 中提供的一项新隐私设置来启用隐私报表变量。

每个报表包可以按如下方式进行配置：
1. 在 Reports &amp; Analytics 中，单击&#x200B;**[!UICONTROL 管理员 &gt; 报表包。]**
1. 选择要在其中收集媒体数据的报表包，然后单击&#x200B;**[!UICONTROL 编辑设置 &gt; 隐私管理。]**

   ![](assets/rsm-privacy-select.png)

1. 单击&#x200B;**[!UICONTROL 启用数据隐私报表]**&#x200B;按钮。**注意：**&#x200B;启用后，这些变量将无法关闭。

   ![](assets/rsm-privacy-enable.png)

1. 启用后，您将看到一则确认消息。

   ![](assets/rsm-privacy-config.png)

1. 现在，保留变量可用于报表。请参阅“同意管理选择退出和同意管理选择加入”。

   ![](assets/rsm-privacy-reports.png)

## 实施

已预定义了三个上下文数据变量，以与隐私报表管理保留变量一起使用。需要由每位实施工程师来决定如何管理和保留这些变量的设置。

有关实施上下文数据变量的常规指导，请参阅[上下文数据变量](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html)。

### SSF

* 上下文数据：`contextData.['cm.ssf']`
* 接受的值：
   * 1 - 发送值“1”时，这表示服务器端转发处于选择退出状态。与此变量配对的值“1”将阻止与 Adobe Audience Manager 共享此命中。请参阅 [AAM ePrivacy 合规性。](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * 此参数不接受其他任何值。

### DMP

* 上下文数据：`contextData.['opt.dmp']`
* 接受的值：
   * N – 发送值“N”时，这表示消费者选择退出共享到数据管理平台。**请注意：**&#x200B;将此变量设置为“N”当前不会阻止共享到 AAM，但是，2020 年初将添加阻止调用 AAM 功能。目前，Adobe 建议将 `c.cm.ssf=1` 和 `c.opt.dmp=N` 都设置为阻止命中项发送到 AAM。
   * Y - 发送值“Y”时，这表示消费者选择加入共享到数据管理平台。

### SELL

* 上下文数据：`contextData.['opt.sell']`
* 接受的值：
   * N - 发送值“N”时，这表示消费者选择退出共享或出售数据给第三方。
   * Y - 发送值“Y”时，这表示消费者选择加入共享或出售数据给第三方。
