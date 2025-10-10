---
description: 可以将加盖时间戳和未加盖时间戳的数据合并到单个报表包中。
title: 时间戳配置
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 6%

---

# 时间戳配置

“[!UICONTROL 时间戳配置]”管理页面允许您为一个或多个报表包启用&#x200B;**[!UICONTROL 可选时间戳]**。 通过此设置，您可以将加盖时间戳和未加盖时间戳的数据合并到单个报表包中。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 可选时间戳]**

## 当前时间戳设置

此部分显示选定报表包的当前时间戳配置。 它可以是以下三个可能值之一：

* **不允许的时间戳（设置`visitorID`受支持）**
* **需要时间戳（不支持设置`visitorID`）**
* **可选时间戳（支持设置`visitorID`，但不在带有时间戳的点击上设置）**

此文本下方是一个标有&#x200B;**[!UICONTROL 将所选报表包转换为可选时间戳]**&#x200B;的复选框。 选中此复选框，然后选择&#x200B;**[!UICONTROL 保存]**&#x200B;为选定的报表包启用[!UICONTROL 可选时间戳]。

## 不允许的时间戳

使用此时间戳配置向报表包发送数据时，时间戳是Adobe的处理服务器收到点击的时间。 如果尝试设置[`timestamp`](/help/implement/vars/page-vars/timestamp.md)变量，则将永久丢弃点击。

## 需要时间戳

使用此时间戳配置将数据发送到报表包时，每次点击都必须包含[`timestamp`](/help/implement/vars/page-vars/timestamp.md)变量。 如果任何点击缺少`timestamp`实施变量，则将永久删除该点击。

启用了时间戳的会话数据会保存长达 92 天。换言之，访问将“保持打开”92天，从而允许在同一访问/会话中包含任何其他点击。 虽然您可以向现有会话添加数据，但Adobe建议按访客顺序添加点击。 每位访客按顺序收到的点击可能会产生意外的报表结果，尽管通过报表时间处理可以缓解其中的许多限制。

## 可选时间戳

“[!UICONTROL 可选时间戳]”设置允许您在多个报表包间集成和报告，无论是否具有[`timestamp`](/help/implement/vars/page-vars/timestamp.md)变量。 [!UICONTROL 可选时间戳]的理想用例包括：

* 在同一个全局报表包中混合加盖时间戳和未加盖时间戳的数据
* 将带有时间戳的数据从移动应用程序发送到全局报表包
* 升级应用程序以使用离线跟踪，而无需创建新报表包

默认情况下，所有新报表包都会启用此设置，除非从具有不同时间戳配置设置的报表包复制了新报表包。

>[!WARNING]
>
>如果您使用[!UICONTROL 可选时间戳]，请不要在加盖时间戳的数据上设置[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。 此操作可能导致数据混乱，并对时间计算（例如逗留时间）、归因、访问次数/访问计数和路径报表产生负面影响。

启用[!UICONTROL 可选时间戳]后，将无法在此界面中禁用它。 在您需要切换回其他时间戳配置设置这种罕见情况下，请与Adobe客户关怀团队联系。
