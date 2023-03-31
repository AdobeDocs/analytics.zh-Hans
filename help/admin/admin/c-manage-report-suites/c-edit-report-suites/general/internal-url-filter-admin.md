---
description: 内部 URL 过滤器可识别您视为存在于网站内部的反向链接。它们可帮助流量源报表填充数据，并且有助于过滤内部流量。
title: 内部 URL 过滤器
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 30%

---


# 内部URL过滤器

内部URL过滤器允许您识别您认为网站内部存在的反向链接。 它们可帮助流量源报表填充数据，并且有助于过滤内部流量。

反向链接或反向链接页面通常指访客通过该链接或页面进入了您的网站。为避免影响数据准确性，您可过滤掉内部的反向链接。报表不包含从[反向链接](/help/components/dimensions/referrer.md)维度、[反向链接域](/help/components/dimensions/referring-domain.md)维度和其他流量源维度中过滤掉的反向链接。

## 查看现有内部URL过滤器

>[!NOTE]
>
>某些报表包具有句点(.)的内部URL过滤器 默认配置。 当存在此过滤器时，所有流量都会被分类为内部流量。 反向链接报表直到句点(.)才起作用 过滤器。

要检查为报表包配置了哪些内部URL过滤器，请执行以下操作： <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. 选择 **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** 以访问报表包管理器。

1. 选择要检查其中配置了哪些内部URL过滤器的报表包，然后选择 **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 内部URL过滤器]**.

   所有现有过滤器均列在 [!UICONTROL **当前过滤器**] 中。

## 向报表包添加内部URL过滤器

1. 选择 **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** 以访问报表包管理器。

1. 选择要添加内部URL过滤器的报表包，然后选择 **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 内部URL过滤器]**.

1. 在添加过滤器部分的提供字段中，开始键入要过滤的页面的URL，然后选择 [!UICONTROL **添加**].

   现在，您添加的URL在 [!UICONTROL **当前过滤器**] 中。
