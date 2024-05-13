---
description: 配置 Experience Cloud 映射的报表包以供在 Advertising Analytics 中使用。
title: 为 Advertising Analytics 启用报表包
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 47%

---

# 为 Advertising Analytics 启用报表包

要在Analytics中查看任何Advertising Analytics搜索数据，您需要为Advertising Analytics报表配置每个Experience Cloud映射的报表包。

1. 导航至&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。

1. 选择映射到您的 Experience Cloud 组织的报表包。
1. 单击 **[!UICONTROL 编辑设置]**>**[!UICONTROL Advertising Analytics 配置]**。

   ![报表](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID指的是要将搜索数据插入其中的Adobe Advertising Cloud(也称为Adobe Media Optimizer)变量。

1. 选择 **[!UICONTROL 不熟悉Advertising Analytics？ 单击此处了解更多信息]** 了解有关Advertising Analytics的更多信息。

1. 设置您希望AMO ID变量使用的变量分配和到期时间。 转化变量 (eVar) 允许 Adobe Analytics 将成功事件归属于特定的变量值。有时候，在一个事件成功之前变量会遇到多个值。对于这类情况，分配将确定哪个变量值可获得该成功事件的信用。

   | 设置 | 定义 |
   |--- |--- |
   | **[!UICONTROL 分配]** | 在以下内容之间选择：<br/> **[!UICONTROL 原始值（第一个）]**：看到的第一个值将获得完全分配点数，无论该变量的后续值是什么。 <br/>**[!UICONTROL 最近（最后一个）]**：看到的最后一个值会获得成功事件的完全分配点数，无论在该值之前触发了什么变量。 |
   | **[!UICONTROL 过期时间]** | 可让您指定一个时段或事件，eVar值将在此时段或事件之后过期（即，不再接收成功事件的信用）。  如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。 |

1. 单击&#x200B;**[!UICONTROL 启用 Advertising Analytics 报表]**（第一次）或&#x200B;**[!UICONTROL 更新 Advertising Analytics 报表]**（第一次之后）。您的报表包现已准备好接收 Advertising Analytics 搜索数据。您现在已准备好 [创建广告帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
