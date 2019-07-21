---
description: 'null'
seo-description: 'null'
seo-title: 警报生成器
title: 警报生成器
uuid: 86d00a33-dc99-4dc3-a732-0b895 ba487 bc
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# 警报生成器

>[!IMPORTANT]
>
>Intelligent Alerts are available to Adobe [!DNL Analytics] Prime and Adobe [!DNL Analytics] Ultimate customers only.

可通过以下四种方法访问警报生成器：

* 在 Analysis Workspace 中使用以下快捷键：

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* From within a [!UICONTROL Reports &amp; Analytics] report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

The Alert Builder interface is familiar to those who have built segments or calculated metrics in [!DNL Analytics]:

![](assets/alert_builder.png)

**警报名称**

指定警报的名称。警报名称可能包含报表名称或量度阈值。

**时间粒度**

指定要何时检查量度：每小时、每天、每周或每月。

>[!NOTE]
>
>对于具有自定义日历的报告套件，我们不支持Alert Builder中的每月粒度。

**收件人**

指定警报的发送地址。An alert can be sent to an [!DNL Analytics] user, an [!DNL Analytics] group, a raw email address, or to a phone number.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

**过期日期**

设置警报的过期日期。

**发送警报时间...**

*...以下任何一个量度触发器*

* 将量度拖放到将添加触发器的画布中。

   Note that an **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.

* 确定触发警报前量度必须超过的阈值。您可以将此值设置为一个阈值，然后设置为下列条件之一：

   * 异常已存在
   * 异常高于预期
   * 异常低于预期
   * 异常超过
   * 大于或等于
   * 小于或等于
   * 更改百分比

* “异常超过”是一个新条件，不同于现有（静态）的阈值。它引入了异常检测算法，能够动态定义触发器。您可以将阈值设置为 90%、95%、99%、99.75% 或 99.9%。
* 每小时粒度的阈值设置为 99.75%，每日粒度的阈值设置为 99%。
* 请注意，您还可以使用计算量度。

*...使用以下过滤器*

通过拖放区段或维度来添加过滤器。例如，添加“仅限移动设备”区段表示仅针对移动设备触发规则。

其他过滤器将通过 AND 语句添加。

**添加规则**

您可以通过单击齿轮图标添加 AND 或 OR 规则。

## 警报预览 {#section_10D75BA7B77E4C5FAF58A719C082E070}

交互式警报预览可根据过去的经验显示警报大致的触发频率。

例如，如果将时间粒度设置为每天，则预览会显示某个量度在过去 30 或 31 天中触发了 x 次警报。

如果您发现触发警报的次数过多，则可以在[警报管理器](/help/components/c-alerts/alert-manager.md)中调整阈值。

![](assets/alert_preview.png)
