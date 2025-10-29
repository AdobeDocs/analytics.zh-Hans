---
description: 内部URL过滤器可识别您视为网站内部的反向链接。 它们有助于流量源报告填充数据并帮助过滤内部流量。
title: 内部 URL 过滤器
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---


# 内部 URL 过滤器

通过内部URL过滤器，可识别您视为网站内部的反向链接。 它们有助于流量源报告填充数据并帮助过滤内部流量。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 内部URL筛选器]**

反向链接或反向链接页面通常是访客进入您网站时所在的页面。 为了避免数据出现偏差，您可以过滤掉内部反向链接。 依赖内部URL过滤器的维度包括[反向链接](/help/components/dimensions/referrer.md)、[反向链接域](/help/components/dimensions/referring-domain.md)、[营销渠道](/help/components/dimensions/marketing-channel.md)和其他流量源维度。

[营销渠道处理规则](../marketing-channels/mc-proc-rules.md)提供“[!UICONTROL 匹配内部URL过滤器]”作为可能的规则条件。

>[!IMPORTANT]
>
>某些报表包默认配置了句点(`.`)的内部URL过滤器。 如果存在此过滤器，则所有流量都将被分类为内部流量。 只有在删除此过滤器并替换为一个或多个所需的内部域后，反向链接报表才能正常工作。

* 查看&#x200B;**[!UICONTROL 当前筛选器]**&#x200B;部分下的所有现有筛选器。
* 使用&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;部分下的文本框添加筛选器，然后单击&#x200B;**[!UICONTROL 添加]**。

筛选器对完整URL使用&#x200B;**contains**&#x200B;逻辑进行操作。 Adobe建议在创建过滤器时省略协议(`https://`)和子域，除非需要将来自单独子域的流量作为外部流量。
