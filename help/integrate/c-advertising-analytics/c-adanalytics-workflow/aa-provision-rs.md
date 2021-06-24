---
description: 配置 Experience Cloud 映射的报表包以供在 Advertising Analytics 中使用。
title: 为 Advertising Analytics 启用报表包
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '281'
ht-degree: 100%

---

# 为 Advertising Analytics 启用报表包

要在 Analytics 中查看任何 Advertising Analytics 搜索数据，您需要配置每个 Experience Cloud 映射的报表包，以便进行 Advertising Analytics 报告。

1. [将报表包映射到组织](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html?lang=zh-Hans)。
1. 导航至&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。

1. 选择映射到您的 Experience Cloud 组织的报表包。
1. 单击 **[!UICONTROL 编辑设置]**>**[!UICONTROL Advertising Analytics 配置]**。

   ![报表](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID 指的是要将搜索数据插入其中的 Adobe Advertising Cloud 变量。

1. 设置您想要 AMO ID 变量使用的变量分配和过期日期。转化变量 (eVar) 允许 Adobe Analytics 将成功事件归属于特定的变量值。有时候，在一个事件成功之前变量会遇到多个值。对于这类情况，分配将确定哪个变量值可获得该成功事件的信用。

   | 设置 | 定义 |
   |--- |--- |
   | 原始值（第一个） | 无论该变量的后续值是什么，所看到的第一个值将获得全部分配点数。 |
   | 最近（上一个） | 无论之前使用了什么变量，所看到的最后一个值将获得成功事件的全部分配点数。 |
   | 过期时间 | 让您可以指定一个时段或事件，eVar 值将在此时段或事件之后过期（即，不再接收成功事件的点数）。如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。 |

1. 单击&#x200B;**[!UICONTROL 启用 Advertising Analytics 报表]**（第一次）或&#x200B;**[!UICONTROL 更新 Advertising Analytics 报表]**（第一次之后）。您的报表包现已准备好接收 Advertising Analytics 搜索数据。现在，您可以[创建广告帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。
