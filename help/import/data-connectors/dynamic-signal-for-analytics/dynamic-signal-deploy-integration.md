---
description: 部署动态信号数据连接器以在Adobe Analytics中使用。
title: 部署集成
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 96%

---


# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，包括完成 Adobe 集成向导和验证集成。

## 完成 Adobe 集成向导{#completing-the-adobe-integration-wizard}

在 Data Connectors 界面中完成集成向导的步骤。

1. 导航到 Adobe Experience Cloud 中的“Data Connectors”（以前称为 Genesis）区域。
1. 启动 Dynamic Signal 集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：

   | 项目 | 描述 |
   |---|---|
   | 电子邮件地址 | 主要联系人的电子邮件地址。 |
   | 描述 | （可选）对此集成设置的描述。 |
   | 社区 ID | 您可以从 Dynamic Signal 代表处获取此 ID。 |

1. 配置以下&#x200B;**[!UICONTROL 变量映射]**&#x200B;项目：

   | 项目 | 描述 |
   |---|---|
   | 跟踪代码 | 从报表包中选择一个可用的 eVar 变量。 |

1. 查看将为此集成创建的分类。
1. 选中用于创建 Dynamic Signal 集成功能板的框（可选，但强烈推荐）。
1. 查看所有配置项目并单击&#x200B;**[!UICONTROL 立即激活]**。
1. **重要信息**：完成向导后，必须通知 Dynamic Signal 代表，以便他们在 VoiceStorm 平台上激活该集成。

## 验证集成{#verifying-the-integration}

查看 Adobe Experience Cloud 中的 Dynamic Signal VoiceStorm 集成设置的步骤

1. 在集成活动日志中查看 Dynamic Signal 集成设置。
   1. 在 Adobe Experience Cloud 中，导航到&#x200B;**[!UICONTROL 支持]** > **[!UICONTROL 集成活动日志]**。

      ![](assets/integration_activity_log.png)

   1. 查找&#x200B;**[!UICONTROL 已成功导入分类数据]**&#x200B;等条目。这些条目应会在成功部署后的 24 小时内显示。
1. 使用通过 Adobe 集成向导自动为您创建的功能板（步骤 7），查看 Adobe Analytics 中的 Dynamic Signal 报表。或者，您也可以导航到 Adobe Analytics 菜单结构中的 Dynamic Signal 报表 - 请参阅以下屏幕快照。

   **注意**：此数据应会在成功部署后的 24-48 小时内显示。

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
