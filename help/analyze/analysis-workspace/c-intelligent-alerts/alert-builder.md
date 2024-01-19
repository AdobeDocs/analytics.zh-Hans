---
description: 当项目组件达到一定的阈值时获取警报。
title: 警报生成器 (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: aae28c90-bfdf-49ff-bd38-c9ef63880bf4
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 100%

---

# 警报生成器

>[!NOTE]
>
>智能警报仅适用于 Adobe Analytics Prime 和 Adobe Analytics Ultimate 客户。

## 访问警报生成器

可通过以下四种方法访问警报生成器：

* 在 Analysis Workspace 中使用以下快捷键：

  `ctrl (or cmd) + shift + a`
* 转到&#x200B;**[!UICONTROL Workspace]** > **[!UICONTROL 组件]** > **[!UICONTROL 新警报]**。
* 选择一个或多个自由格式表行项目，单击鼠标右键并选择&#x200B;**[!UICONTROL 从选定范围中创建警报]**。

## 构建警报

警报生成器界面与 Analytics 中具有生成区段或计算量度的界面相似：

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**警报名称**

指定警报的名称。警报名称可能包含报表名称或指标阈值。

**时间粒度**

指定要何时检查指标：每小时、每天、每周或每月。

>[!NOTE]
>
>对于包含自定义日历的报表包，警报生成器不支持每月粒度。

**收件人**

指定警报的发送地址。可以将警报发送给 Analytics 用户、Analytics 组、原始电子邮件地址或电话号码。

>[!IMPORTANT]
>
>电话号码前必须加上“+”和[国家/地区代码](https://countrycode.org/)。

触发警报后用户将收到类似于以下内容的电子邮件：

![](assets/alerts-email.PNG)

**过期日期**

设置警报的过期日期。

**发送警报时间...**

*...以下任何一个指标触发器*

* 将量度拖放到将添加触发器的画布中。

  如果警报中有组件（量度/维度/区段）与当前选中的报表包不兼容，则会显示&#x200B;**“组件不兼容”**&#x200B;消息。
* 确定触发警报前指标必须超过的阈值。您可以将此值设置为一个阈值，然后设置为下列条件之一：

   * 异常已存在
   * 异常高于预期
   * 异常低于预期
   * 大于或等于
   * 小于或等于
   * 更改百分比
   * 您可以将阈值设置为 90%、95%、99%、99.75% 或 99.9%。

  请注意，您还可以使用计算量度。

*...使用以下过滤器*

* 通过拖放区段或维度来添加过滤器。例如，添加“仅限移动设备”区段表示仅针对移动设备触发规则。
* 其他过滤器将通过 AND 语句添加。

**添加规则**

您可以通过单击齿轮图标添加 AND 或 OR 规则。

## 预览警报 {#section_10D75BA7B77E4C5FAF58A719C082E070}

交互式警报预览可根据过去的经验显示警报大致的触发频率。

例如，如果将时间粒度设置为每天，则预览会显示某个指标在过去 30 或 31 天中触发了 x 次警报。

如果您发现触发警报的次数过多，则可以在[警报管理器](/help/components/c-alerts/alert-manager.md)中调整阈值。

![](assets/alert_preview.png)
