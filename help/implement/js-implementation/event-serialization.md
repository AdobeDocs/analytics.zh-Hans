---
description: 事件序列化是实施措施以防止重复事件进入 Analytics 报告的过程。此过程通常发生在用户多次刷新页面、多次导航到某个特定页面，或者将网页保存到其计算机时（例如，如果客户将购买确认页面保存到其计算机，则在未实施事件序列化的情况下，每次查看该页面，都会重复计数订购和收入）。
keywords: Analytics 实施
seo-description: 事件序列化是实施措施以防止重复事件进入 Analytics 报告的过程。此过程通常发生在用户多次刷新页面、多次导航到某个特定页面，或者将网页保存到其计算机时（例如，如果客户将购买确认页面保存到其计算机，则在未实施事件序列化的情况下，每次查看该页面，都会重复计数订购和收入）。
seo-title: 活动序列化概述
solution: Analytics
title: 活动序列化概述
topic: 开发人员和实施
uuid: 8c7883bb-5ba4-4440-af80-c0 d1586770 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 活动序列化概述

事件序列化是实施措施以防止重复事件进入 Analytics 报告的过程。此过程通常发生在用户多次刷新页面、多次导航到某个特定页面，或者将网页保存到其计算机时（例如，如果客户将购买确认页面保存到其计算机，则在未实施事件序列化的情况下，每次查看该页面，都会重复计数订购和收入）。

[!UICONTROL 事件序列化]在下列情况下非常有用：

* 页面可能被重新载入或刷新，重复发送事件。[!UICONTROL 事件序列化]通过为每个事件使用一个序列号来防止事件被重复计数。
* 用户将页面保存到他/她的计算机中，以备以后查看。这种情况对于用来查看购买回执的购买确认页面十分常见。[!UICONTROL 事件序列化]可防止后续的页面重新载入对事件重复计数。

>[!NOTE]
>
>数据源不支持事件序列化或重复重读。

本文档介绍了用于为“[!UICONTROL 转化]”和“[!UICONTROL 自定义]”事件实施“[!UICONTROL 事件序列化]”的过程。To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . 然后，选择要在“[!UICONTROL 独特事件记录]”列中记录哪些事件。

## 默认行为 {#section_892BB2BEFC434B69869D4504A8B54308}

默认行为会计入事件的每个实例。为计入的每个 [!UICONTROL pageview] 设置一个事件，甚至包括页面重新载入或刷新。使用 [!UICONTROL s.purchaseID] 变量来唯一标识每个订购（购买）。这样，用户可以重新加载订购页面，而不会重复计数订购、收入或产品。类似功能适用于所有事件。其中包括预定义的事件（如 [!UICONTROL prodView] 和 [!UICONTROL scCheckout]）以及所有自定义事件。

<!-- 

event_serialization_impl.xml

 -->

To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . 然后，选择要在“[!UICONTROL 独特事件记录]”列中记录哪些事件。可以将事件设置为三个不同的设置。

**始终记录事件**：这是所有事件最初启用时的默认行为。图像请求中包括的所有事件（包括页面重新载入）将会直接发送到 Analytics。

**每次访问记录一次**：启用此设置的事件将仅跟踪给定访问中该事件的第一个实例。新访问开始之后，可以再次跟踪启用了此设置的每个事件。这是通过浏览器刷新消除重复事件的有效方式。

**使用事件 ID**：此设置可以将每个事件与唯一的 ID 相关联。如果 Analytics 在使用该变量之前已发现某个事件 ID，则报告将不会把此事件计算在内。

唯一无法启用事件序列化的事件是购买事件，因为该事件使用 s.purchaseID 变量。所有其他电子商务事件和自定义事件都可以启用这些设置。

* 使用唯一标识符可让一个事件对应每个唯一 ID 触发一次。
* 发送多个事件，然后配置 Analytics 以允许一个事件对应每次访问触发一次。

若要实施[!UICONTROL 事件序列化]，请提供事件的唯一 ID，例如 event1:1234ABCD。

## 事件序列化 - 对应每个唯一 ID 触发一次 {#section_8806E48B497546F5A335383FB8627694}

在[!UICONTROL 事件序列化]已实施，并且 [!DNL Analytics] 收到一个重复值时，它将忽略该事件。一个事件对应每个唯一值只计入一次。如果数值是唯一的，则计入另一个事件实例，如以下示例中所示：

| 用户名 | 描述 | 事件语法 | Analytics Event1 总计数 |
|---|---|---|---|
| John | 用户第一次查看页面。 | event1:1000 | 1 |
| John | 用户重新加载页面（表单提交可能失败，并导致页面重新加载）。 | event1:1000 | 1 |
| Stacy | 用户第一次查看页面。 | event1:1001 | 2 |
| Stacy | 用户重新加载页面（表单提交可能失败，并导致页面重新加载）。 | event1:1001 | 2 |
| Jill | 用户第一次查看页面，正确输入信息，并移至下一页面。 | event1:1002 | 3 |
| Jamie | 用户第一次查看页面 | event1 | 4 |
| Jamie | 用户忘记填写表单上的“姓氏”字段。表单将再次显示，并突出显示缺少的信息。 | event1 | 5 |

选择序列化 ID 时请注意以下事项：

* 序列化 ID 不得超过 20 个字符。
* 序列化 ID 必须为字母数字字符。
* 每个成功事件的序列化 ID 都是独立的。因此，如果需要，您可以对多个成功事件使用同一 ID，而不是只对同一个成功事件。
* 序列化 ID 与报表包绑定在一起。因此，如果您使用多包标记向多个报表包发送数据，请留意这一点。
* 序列化 ID 永远不会过期，因此，即使在数年后再次使用同一 ID，成功事件也不会进行被再次计数。
* 删除 Cookie 不会阻碍事件 ID 序列化，因为序列化 ID 存储在 Adobe 服务器上，而不是以 Cookie 为基础。
* 无法使用事件 ID 序列化的成功事件是购买事件，该事件使用特殊的 s.purchaseID 变量进行序列化。

## 事件序列化 - 每次访问触发一次 {#section_C919D44F321A47FBBF043D0C57A2A050}

[!DNL Analytics] 的一项功能是允许某个事件在每次访问时只触发一次。

This can be enabled from the UI:  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]** .
