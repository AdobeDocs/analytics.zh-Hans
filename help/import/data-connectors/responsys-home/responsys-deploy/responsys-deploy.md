---
description: 部署Responsys数据连接器以在Adobe Analytics中使用。
title: 部署集成
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 96%

---


# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，只需执行以下操作：

## 完成 Adobe 集成向导{#completing-the-adobe-integration-wizard}

在 Data Connectors 界面中完成集成向导的步骤。

1. 导航到 Adobe Experience Cloud 中的“Data Connectors”（以前称为 Genesis）区域。
1. 启动 Responsys 集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：

   | 项目 | 描述 |
   |---|---|
   | 电子邮件地址 | 主要联系人的电子邮件地址 |
   | 描述 | （可选）对此集成设置的描述 |
   | 帐户 ID | 通过 support@responsys.com 联系 Responsys 支持团队获取 |

1. 配置以下&#x200B;**[!UICONTROL 变量映射]**&#x200B;项目：

   | 项目 | 描述 |
   |---|---|
   | 消息 ID | 选择一个用于实时收集消息 ID 的 eVar。 |
   | 收件人 ID | 选择一个用于实时收集收件人 ID 的 eVar。 |
   | 退回总计 | 选择一个用于从 Responsys 接收每日退回量的数字事件。 |
   | 已发送电子邮件 | 选择一个用于从 Responsys 接收每日发送量的数字事件。 |
   | 已点击 | 选择一个用于从 Responsys 接收每日总点击量的数字事件。 |
   | 已打开 | 选择一个用于从 Responsys 接收每日总打开量的数字事件。 |
   | 已取消订阅 | 选择一个用于从 Responsys 接收每日取消订阅量的数字事件。 |
   | 已送达 | 选择一个用于从 Responsys 接收每日送达量的数字事件。 |

1. 启用数据访问并配置数据收集。
   1. 根据需要重命名分类。
   1. **[!UICONTROL 合作伙伴区段]**&#x200B;是包含在集成中的标准再营销区段。
   1. 在&#x200B;**[!UICONTROL 访问请求]**&#x200B;下，选中允许将产品信息导出到 Responsys 中的每日再营销区段的框。
   1. 配置收集 ID 的方式：通过手动更新 Analytics 收集代码还是使用自动解决方案。如果选择&#x200B;**[!UICONTROL 自动解决方案]**，则必须包含电子邮件链接中用于传递 ID 的参数。
1. 查看所有配置项目并单击&#x200B;**[!UICONTROL 立即激活]**。

## 在 Responsys 系统内配置{#configuring-within-the-responsys-system}

激活集成的过程涉及联系 Responsys 支持团队。

完成集成向导后，必须在 Responsys 内激活集成。

为此，请通过 support@responsys.com 联系 Responsys 支持团队。
