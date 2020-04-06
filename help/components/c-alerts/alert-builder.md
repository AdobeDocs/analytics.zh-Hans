---
description: 'null'
title: 警报生成器
uuid: 86d00a33-dc99-4dc3-a732-0b895ba487bc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 警报生成器

>[!IMPORTANT]
>
>智能警报仅适用于 Adobe [!DNL Analytics] Prime 和 Adobe [!DNL Analytics] Ultimate 客户。

通过以下四种方式之一访问警报生成器：

* 在分析工作区中使用以下快捷键：

   `ctrl (or cmd) + shift + a`
* 转到 **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**。
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* 从报告 [!UICONTROL Reports & Analytics] 中，转到 **[!UICONTROL More]** > **[!UICONTROL Add Alert]**。

警报生成器界面与 [!DNL Analytics] 中具有生成区段或计算量度的界面相似：

![](assets/alert_builder.png)

**警报名称**

指定警报的名称。 警报名称可能包含报告名称或度量阈值。

**时间粒度**

指定要何时检查量度：每小时、每天、每周或每月。

>[!NOTE] 对于包含自定义日历的报表包，警报生成器不支持每月粒度。

**收件人**

指定警报的发送地址。可以将警报发送给 [!DNL Analytics] 用户、[!DNL Analytics] 组、原始电子邮件地址或电话号码。

>[!IMPORTANT]
>
>电话号码前必须加上“+”和[国家/地区代码](https://countrycode.org/)。

**过期日期**

设置警报的过期日期。

**发送警报时间...**

*...以下任何一个量度触发器*

* 将量度拖放到将添加触发器的画布中。

   请注意，如果警报中有组件（量度/维度/区段）与当前选中的报表包不兼容，则会显示&#x200B;**“组件不兼容”**&#x200B;消息。

* 确定在设置警报之前度量必须超过的阈值。 您可以将此值设置为阈值，然后设置为以下条件之一：

   * 异常已存在
   * 异常高于预期
   * 异常低于预期
   * 异常超出
   * 高于或等于
   * 低于或等于
   * 更改依据

* “异常超出”是超越现有（静态）阈值的新条件。 它引入了异常检测算法，这些算法可动态定义触发器。 您可以将阈值设置为 90%、95%、99%、99.75% 或 99.9%。
* 每小时粒度设置为99.75%阈值，每日粒度设置为99%。
* 请注意，您还可以使用计算量度。

*...使用以下过滤器*

拖放区段或维度以添加过滤器。 例如，添加“仅限移动设备”区段意味着规则仅针对移动设备触发。

将使用AND语句添加其他过滤器。

**添加规则**

您可以通过单击齿轮图标添加 AND 或 OR 规则。

## 警报预览 {#section_10D75BA7B77E4C5FAF58A719C082E070}

交互式警报预览显示根据以往经验触发警报的频率（大约）。

例如，如果将时间粒度设置为每日，预览会告诉您，在过去30或31天内，某个度量x次将触发警报。

如果您发现触发的警报过多，可以在警报管理器中调整 [阈值](/help/components/c-alerts/alert-manager.md)。

![](assets/alert_preview.png)
