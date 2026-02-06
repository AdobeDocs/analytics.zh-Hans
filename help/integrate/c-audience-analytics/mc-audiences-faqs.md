---
description: 实施 Audience Analytics 时可能遇到的问题的解答。
solution: Experience Cloud
title: Audience Analytics 常见问题解答。
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: 3aa8ce6af928693fd08d42be6e7dd2b939566804
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 16%

---

# 常见问题解答

实施 Audience Analytics 时可能遇到的问题的解答。

## 法律方面的常见问题解答 {#legal}

+++ 如何知道我的Analytics数据中是否有个人身份信息(PII)？ 如果有，我该怎么做？

如果您在prop或eVar中有电子邮件/地址/等，请考虑在收集期间对数据进行哈希处理。 如果您的国家/地区将IP地址视为PII，请[启用IP模糊处理](/help/admin/tools/exclude-ip.md)。 咨询您的Analytics管理员，查看您正在收集的内容。 请咨询您的法律部门，了解他们对PII的看法。

+++

+++ 如何知道我的报表包是进行现场个性化还是异地/现场定位？

这不适用于将Adobe Analytics数据发送到Adobe Audience Manager。 问问自己：

* 您是否会将与MCA维度共享的Analytics共享区段返回到Experience Cloud？

* 是否导出（例如通过数据馈送）到用于这些目的的Business Intelligence (BI)系统？

+++

## Adobe Audience Manager特定的常见问题解答 {#aam-specific}

+++ 如何在Audience Manager中创建Analytics目标？

请参阅[在Adobe Audience Manager中配置Analytics目标](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=zh-Hans)。

+++

+++ 创建和保存Analytics目标后，需要多长时间才能将数据显示在我选择的报表包中？

向报表包填充新数据可能需要几个小时。

+++

+++ 我已创建了一个新的Analytics目标，但在可用区段的“目标映射”部分中看不到该目标。 这个目的地在哪里，我怎么找到它？

当您在&#x200B;**[!UICONTROL 区段映射]**&#x200B;中选择&#x200B;**[!UICONTROL 自动映射所有当前和未来区段]**&#x200B;选项时，Analytics目标会从区段的“目标映射”部分中消失。 要防止出现这种情况，请选择&#x200B;**[!UICONTROL 手动映射区段]**，而不是自动选项。

+++

+++ 在Analytics中，这是否会为我提供Adobe Audience Manager中的所有信息？

不会，只有与启用Audience Manager受众期间或之后以及区段资格期间/之后访问您网站的人员相关的数据。

+++

+++ 这可提供每个区段的可寻址受众总数吗？

不算是。 它将告知您在区段资格期间或之后访问您网站的区段中的访客数量。

+++

+++ 这与Analytics的旧版Cookie目标有何不同？

区段在同一点击中实时进行资格鉴定和返回。 友好名称会自动显示。

+++

+++ 如果我的某些报表包包含个人数据，而另一些没有，该怎么办？&lt;

提示：创建两个维度 — 将个人数据报表包添加到其中一个维度，并将非个人数据报表包添加到另一个维度。

+++

## Analytics特定的常见问题解答 {#aa-specific}

+++ 此集成在Analytics中会作为维度还是区段显示？

作为维度：受众ID和受众名称。

+++

+++在Analytics中，可以在何处使用这些维度？

随时随地；这些维度的处理方式与在Analytics中收集的任何其他维度相同。

+++

+++ 为什么在Analytics中看不到传入的数据？

数据源和目标之间的Adobe Audience Manager隐私控件可能存在冲突。

+++

+++ 即使我已选择发送所有区段，为什么在Analytics中仍会缺少某些区段？&lt;

* 目标数据源和区段数据源中的Adobe Audience Manager数据导出控件可能存在冲突，这会阻止发送某些区段。

* 如果您在区段中使用第三方数据特征，这些区段无法共享到包含个人数据的目标（一组报表包）。

+++

+++ 为什么我在Analytics报表中看到“已达到受众限制”？ (注意：这在Data Warehouse中还将表示为Audience ID = -1和`::max_audiences_exceeded::`)

默认情况下，Adobe Audience Manager的Audience Analytics集成会按每次点击将所有访客符合条件的区段发送到Analytics。 如果某位访客在一次点击中属于超过150个Adobe Audience Manager区段，则会将&#x200B;**150个最近限定的区段**&#x200B;发送到Analytics，而其余列表将被截断。 此外，还会向 Analytics 发送一个标记，指示区段列表被截断，该标记在“受众名称”维度中显示为“已达到受众限制”，在“受众 ID”维度中显示为“-1”。

虽然访客不太可能在一次点击中有资格使用 150 个以上的区段，但这种情况依然有极小的概率发生。如果您在报表中遇到“已达到受众限制”，可选择以下两个选项：

* 选项1：继续让集成以现成状态工作，为特定访客发送150个最近符合条件的区段。

* 选项2：在Adobe Audience Manager中，选择对您的业务最重要的150个区段进行集成。 然后，Adobe Audience Manager仅根据这150个区段检查访客。 此方法的缺点是，您在所有访客中仅会收到这150个区段。 另一方面，由于集成的按点击性质，选项1方法可提供无限区段。

+++

+++ 对于此集成，Analytics是否需要为额外的服务器调用付费？

否。Adobe Audience Manager受众已纳入Analytics点击服务器端。 这不会产生对Analytics（主要或次要）的额外服务器调用。

+++

## 服务器端转发(SSF)常见问题 {#SSF}

+++ 如果我实施了旧版SSF，我是否还需要转到Analytics“管理员”并打开报表包SSF？

是的。在Adobe Audience Manager目标设置中，您将只看到启用了SSF的报表包。

+++

+++ 为什么我无法在Analytics管理员中为某些报表包启用SSF？

只能启用映射到您的 Experience Cloud 组织的报表包。

有关此主题的更多常见问题解答，请参阅[服务器端转发常见问题解答](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)。

+++

## 一般常见问题解答 {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ 为什么Audience Manager与Analytics之间的区段访客计数不同？

查看[访客计数差异](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md)。

+++

+++ Adobe Audience Manager中的“受众”与Analytics中的“区段”有何区别？

请参阅[了解Analytics和Audience Manager中的区段](/help/integrate/c-audience-analytics/aam-analytics-segments.md)。 Adobe Audience Manager受众作为要在Analytics中使用的“维度”组件进行发送和共享。 例如，它们在区段生成器中不显示为区段，而是显示为可用于生成区段的维度。

+++

+++ 从Adobe Audience Manager集成的客户属性和客户数据之间有何区别？

客户属性不是基于时间的；它们可以追溯应用，并可以向前发展。 Adobe Audience Manager集成数据是基于时间的，并且仅用于前进。 此外，客户属性是Experience Cloud访客ID的查找表，而Adobe Audience Manager集成是将数据拼合到访客的每次点击中。

+++

+++ 对于此问题的传统方法（例如，旧的测试版或“咨询”插件Cookie目标）怎么样了？

我们建议您实施新集成并删除旧目标。

+++
