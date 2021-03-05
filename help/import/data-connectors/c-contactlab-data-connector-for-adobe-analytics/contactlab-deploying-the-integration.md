---
description: 部署ContactLab集成以在Adobe Analytics中使用。
title: 部署集成
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 97%

---


# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，只需执行以下操作：

## 完成 Adobe 集成向导{#completing-the-adobe-integration-wizard}

在 Data Connectors 界面中完成集成向导的步骤。

1. 导航到 Adobe Experience Cloud 中的“Data Connectors”（以前称为 Genesis）区域。
1. 启动 ContactLab 集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：

   | 项目 | 描述 |
   |---|---|
   | 电子邮件地址 | 主要联系人的电子邮件地址 |
   | 描述 | （可选）对此集成设置的描述 |

1. 配置以下&#x200B;**[!UICONTROL 变量映射]**&#x200B;项目：

   | 项目 | 描述 |
   |---|---|
   | 链接 ID | 选择一个用于实时收集链接 ID 的 eVar。 |
   | 消息 ID | 选择一个用于实时收集消息 ID 的 eVar。 |
   | 收件人 ID | 选择一个用于实时收集收件人 ID 的 eVar。 |
   | 退回 | 选择一个用于从 ContactLab 接收每日退回量的数字事件。 |
   | 已发送 | 选择一个用于从 ContactLab 接收每日发送量的数字事件。 |
   | 已点击 | 选择一个用于从 ContactLab 接收每日总点击量的数字事件。 |
   | 已打开 | 选择一个用于从 ContactLab 接收每日总打开量的数字事件。 |
   | 已取消订阅 | 选择一个用于从 ContactLab 接收每日取消订阅量的数字事件。 |

1. 启用数据访问并配置数据收集。
   1. 根据需要重命名分类。
   1. **[!UICONTROL 合作伙伴区段]**&#x200B;是包含在集成中的标准再营销区段。
   1. 在&#x200B;**[!UICONTROL 您的区段]**&#x200B;下，选择要包含在此集成中的任何自定义区段。您可以在管理面板下创建其他自定义区段。
   1. 在&#x200B;**[!UICONTROL 访问请求]**&#x200B;下，选中允许将产品信息导出到 ContactLab 中的每日再营销区段的框。
   1. 根据需要重命名计算量度。
   1. 配置收集 ID 的方式：通过手动更新 Analytics 收集代码还是使用自动解决方案。如果选择&#x200B;**[!UICONTROL 自动解决方案]**，则必须包含电子邮件链接中用于传递 ID 的参数。
1. 查看所有配置项目并单击&#x200B;**[!UICONTROL 立即激活]**。

## 验证集成{#verifying-the-integration}

查看 Adobe Experience Cloud 中的 ContactLab 集成设置

1. 查看集成活动日志。
   1. 在 Adobe Experience Cloud 中，导航到&#x200B;**[!UICONTROL 支持]** > **[!UICONTROL 集成活动日志]**。

      ![](assets/integration_activity_log.png)

   1. 查找&#x200B;**[!UICONTROL 已成功导入分类数据]**、**[!UICONTROL 已成功导入量度数据]**、**[!UICONTROL 已成功导出量度数据]**&#x200B;等条目。这些条目应会在成功部署后的 1 天内显示。
1. 查看 Adobe Analytics 中的报表数据。
   1. 导航到&#x200B;**[!UICONTROL 自定义转化]** > **[!UICONTROL 自定义转化 1-10]** > **[!UICONTROL 消息 ID 报表]**。

      ![](assets/reporting.png)

   1. 查找 ContactLab 报表。此数据应会在成功部署后的 24-48 小时内显示。
