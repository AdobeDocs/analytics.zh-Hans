---
description: 配置 Experience Cloud 映射的报表包以供在 Advertising Analytics 中使用。
title: 为 Advertising Analytics 启用报表包
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
TQID: https://experienceleague.adobe.com/sGEXiz2RiDhf9p-2df76o-XxBERTKPB-O-rZeIb4BBI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 27%

---

# 为 Advertising Analytics 启用报表包

要在Analytics中查看任何Advertising Analytics搜索数据，您需要为Advertising Analytics报表配置每个Experience Cloud映射的报表包。

1. 导航至&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。

1. 选择映射到您的 Experience Cloud 组织的报表包。
1. 单击 **[!UICONTROL 编辑设置]**>**[!UICONTROL Advertising Analytics 配置]**。

   ![报表](assets/aa-reporting.png)

1. 选择&#x200B;**[!UICONTROL 不熟悉Advertising Analytics？ 单击此处了解更多信息]**，了解有关Advertising Analytics的更多信息。

1. 设置您希望AMO ID变量使用的变量分配和到期时间。 转化变量(eVar)允许Adobe Analytics将成功事件归因于特定变量值。 有时，变量在点击成功事件之前会遇到多个值。 对于这些情况，分配决定了哪个变量值将获得事件的点数。

   | 设置 | 定义 |
   |--- |--- |
   | **[!UICONTROL 分配]** | 选择范围： <br/> **[!UICONTROL 原始值（第一个）]**：看到的第一个值将获得完全分配点数，无论该变量的后续值是什么。 <br/>**[!UICONTROL 最近（最后一个）]**：看到的最后一个值将获得成功事件的完全分配点数，无论在该值之前触发了什么变量。 |
   | **[!UICONTROL 过期时间]** | 可让您指定时段或事件，eVar值将在此时段或事件之后过期（即，不再接收成功事件的信用）。  如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。 |

1. 单击&#x200B;**[!UICONTROL 启用Advertising Analytics报表]**（第一次），或单击&#x200B;**[!UICONTROL 更新Advertising Analytics报表]**（后续时间）。 您的报表包现在可以接收Advertising Analytics搜索数据。 您现在已准备好[创建Advertising帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。
