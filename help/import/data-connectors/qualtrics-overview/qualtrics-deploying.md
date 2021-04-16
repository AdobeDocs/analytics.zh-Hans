---
description: 部署此集成的流程非常简单，只需执行以下操作。
subtopic: Qualtrics
title: 部署集成
feature: Data Connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
exl-id: 8637f13d-a07e-412e-9ad7-8a0836301dd6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 98%

---

# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，只需执行以下操作。

## 完成 Adobe 集成向导{#completing-the-adobe-integration-wizard}

要激活集成，必须在 Data Connectors 界面中完成 Qualtrics 集成向导

1. 导航到 Data Connectors 并启动 Qualtrics 集成向导。
1. 选择要用于此集成的报表包，并提供一个名称。

   提供以下步骤中所述的信息，以完成集成向导。1. **向导步骤 1**

   | 电子邮件地址 | 主要联系人的电子邮件地址。 |
   |---|---|
   | 描述 | （可选）对此集成设置的描述。 |
   | Qualtrics 组织 ID | [查找 Qualtrics 组织 ID](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe SiteCatalyst 令牌 | [生成 Qualtrics Adobe Analytics 令牌](../qualtrics-overview/qualtrics-token.md) |

1. **向导步骤 2 - 变量映射**
| Qualtrics 响应列表 | 从报表包中选择一个可用的列表变量。（您可能需要在报表包管理器中启用新的 listVar。）|
|---|---|
| Qualtrics 响应 ID | 从报表包中选择一个可用的 eVar 或 prop。（您可能需要在报表包管理器中启用新的 listVar。）|
| 跟踪服务器 | 提供用于跟踪 Adobe Analytics 数据的跟踪服务器（域）设置。使用 
`trackingServerSecure` 跟踪服务器（如果它与标准跟踪服务器设置不同）。|
| Qualtrics 调查提交 | 从报表包中选择一个可用的事件（您可能需要在报表包管理器中启用新事件）。|

1. **向导步骤 3**：无需执行操作，仅显示相应信息。

   步骤结果 1. **向导步骤 4 - 导出设置**

   | eVar | 选择最多 5 个要显示以导出到 Qualtrics 的 eVar |
   |---|---|
   | 事件 | 选择最多 5 个要显示以导出到 Qualtrics 的自定义事件 |
   | Prop | 选择最多 5 个要显示以导出到 Qualtrics 的 Prop |
   | 访问请求 | 选中要导出到 Qualtrics 的任何标准量度和维度对应的框。需要 `visitor_id` 才能正常执行导出。 |

1. **向导步骤 5**：查看配置，然后单击&#x200B;**[!UICONTROL 立即激活]**。

## 在 Qualtrics Research Suite 中启用集成{#enabling-the-integration-in-qualtrics-research-suite}

完成集成向导后，必须为要连接的每个 Qualtrics 调查激活集成。

1. 登录到 Qualtrics Research Suite。
1. 在&#x200B;**[!UICONTROL 我的调查]**&#x200B;选项卡上，单击要集成的调查所对应的&#x200B;**[!UICONTROL 编辑]**&#x200B;按钮。
1. 单击&#x200B;**[!UICONTROL 高级选项]**&#x200B;菜单，然后选择 **[!UICONTROL Adobe Analytics]**。（如果看不到此选项，请向您的管理员请求获取所需的权限）。

   ![](assets/advanced_options.png)

1. 选择 Adobe Analytics 配置，然后单击&#x200B;**[!UICONTROL 保存]**。如果没有可用的配置，则您可能尚未完成 Adobe 集成向导。
   1. **[!UICONTROL 包括部分响应]**&#x200B;复选框可用于指示您希望在部分完成每个调查屏幕后将数据捕获到 Adobe Analytics 中。如果未选中此项，则只为完全完成的调查传输数据。
   1. 仅当与配置为接收带时间戳的数据（不常见）的报表包集成时，才应使用&#x200B;**[!UICONTROL 发送带有信标的时间戳]**&#x200B;复选框。

   ![](assets/integration_config.png)

## 验证集成{#verifying-the-integration}

完成所有部署步骤后，您可以验证集成是否可成功传输数据。

1. **集成活动日志**：在 Data Connector UI 中，查看 Qualtrics 集成的&#x200B;**[!UICONTROL 支持]**&#x200B;选项卡。在&#x200B;**[!UICONTROL 集成活动日志]**&#x200B;标题下，您应当看到说明已成功导入分类数据的条目。

   >[!NOTE]
   >
   >这些条目应会在成功部署后的 1 小时内显示。

   ![](assets/verify-1.png)

1. **报表数据**：通过在 Marketing Reports and Analytics UI 中导航 Qualtrics 调查报表（位于&#x200B;**[!UICONTROL 列表变量]**&#x200B;下），查看 Qualtrics 调查报表。

   >[!NOTE]
   >
   >如果集成调查主动接收响应，则这些数据应会在成功部署后的 24-48 小时内显示。

   ![](assets/verify-2.png) ![](assets/verify-3.png)
