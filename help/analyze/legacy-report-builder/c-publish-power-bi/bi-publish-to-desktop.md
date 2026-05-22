---
description: 介绍如何将 Report Builder 发布的资产提取到 Power BI Desktop
title: 将已发布的资产提取到 Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 60%

---

# 将已发布的资产提取到 Power BI Desktop

{{legacy-arb}}

介绍如何将 Report Builder 发布的资产提取到 Power BI Desktop

## 先决条件 {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* 您需要安装最新的Power BI桌面版本（2017年4月版）
* 此过程假定您已经向Power BI服务发布了Report Builder格式的表或请求。

## 过程 {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

在2017年4月的Power BI Desktop更新中，Microsoft发布了连接到Power BI服务中数据集的功能。 此功能允许您根据已发布到云的现有数据集创建新报告。 您可以利用此功能更好地协作并减少团队中的重复工作。

1. 在 Power BI Desktop 中，转到&#x200B;**[!UICONTROL 文件]** > **[!UICONTROL 选项和设置]** > **[!UICONTROL 选项]** > **[!UICONTROL 预览功能]**。
1. 启用 **[!UICONTROL Power BI 服务实时连接]**&#x200B;并单击&#x200B;**[!UICONTROL 确定]**。 ![单击“Power BI 服务实时连接”，然后单击“确定”。](assets/bi-preview-features.png)

1. 重新启动 Power BI Desktop。
1. 重新启动桌面后，请转到&#x200B;**[!UICONTROL 主页]** > **[!UICONTROL 获取数据]** > **[!UICONTROL 更多...]**。
1. 搜索并选择 **[!UICONTROL Power BI 服务]**。
1. 在 **[!UICONTROL Microsoft Power BI 服务]** > **[!UICONTROL 我的工作区]**&#x200B;下方，选择之前从 Report Builder 发布的数据集。

有关更多信息，请参阅 [Microsoft 博客帖子](https://powerbi.microsoft.com/zh-cn/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/)。
