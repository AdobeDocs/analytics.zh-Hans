---
description: 内部 URL 过滤器可识别您视为存在于网站内部的反向链接。它们可帮助流量源报表填充数据，并且有助于过滤内部流量。
title: 内部 URL 过滤器
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 31%

---


# 内部 URL 过滤器

通过内部URL过滤器，可识别您视为网站内部的反向链接。 它们可帮助流量源报表填充数据，并且有助于过滤内部流量。

**[!UICONTROL 分析]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 内部URL过滤器]**

反向链接或反向链接页面通常指访客通过该链接或页面进入了您的网站。为避免影响数据准确性，您可过滤掉内部的反向链接。依赖内部URL过滤器的Dimension包括 [反向链接](/help/components/dimensions/referrer.md)， [反向链接域](/help/components/dimensions/referring-domain.md)， [营销渠道](/help/components/dimensions/marketing-channel.md)和其他流量源维度。

[营销渠道处理规则](../marketing-channels/c-rules.md) 提供&quot;[!UICONTROL 匹配内部URL过滤器]”作为可能的规则条件。

>[!IMPORTANT]
>
>某些报表包的内部URL过滤器采用句点(`.`)进行默认配置。 如果存在此过滤器，则所有流量都将被分类为内部流量。 只有在删除此过滤器并替换为一个或多个所需的内部域后，反向链接报表才能正常工作。

* 查看下的所有现有筛选器 **[!UICONTROL 当前筛选器]** 部分。
* 使用 **[!UICONTROL 添加筛选器]** 部分，然后单击 **[!UICONTROL 添加]**.

过滤器使用 **包含** 针对完整URL的逻辑。 Adobe建议忽略协议(`https://`)和子域创建过滤器时的流量，除非需要将来自单独子域的流量作为外部流量。
