---
description: 在Adobe Admin Console中管理Analytics用户及其资源。
title: 管理Analytics用户和资产
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
TQID: https://experienceleague.adobe.com/d8CK9Vf-eaEU6P9386J1eO-JpD5u4l3VoqRcMwvXcW0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 9%

---

# 管理旧版用户帐户、资产和过期日期

您可以使用&#x200B;**[!UICONTROL 管理员] > [!UICONTROL 所有管理员] > [!UICONTROL Analytics用户和管理员]**&#x200B;管理旧版用户帐户、其迁移状态、到期数据、将资产传输到其他用户等。

“用户”屏幕显示当前Adobe Analytics用户的列表，其中包括以下列：

| 列 | 描述 |
|---|---|
| [!UICONTROL 用户 ID] | 用户用于登录到Adobe Analytics的用户ID。 |
| [!UICONTROL 名称] | 用户的名称。 |
| [!UICONTROL 迁移状态] | 从旧用户帐户迁移到Enterprise ID或Adobe ID的状态。  状态可以是“未启动”、“已排队”或“已迁移”。 |
| [!UICONTROL 电子邮件] | 用户的邮箱。 |
| [!UICONTROL 旧版登录] | 旧版登录的状态，可为“启用”或“禁用”。 |
| [!UICONTROL 创建日期] | 在Adobe Analytics中创建用户帐户的时间戳。 |
| [!UICONTROL 上次Analytics访问权限] | 用户帐户最近访问Adobe Analytics的时间戳， |
| [!UICONTROL 有效期限] | 用户帐户的到期日期；如果用户帐户没有到期，则为“无”。 |

![用户](assets/users.png)

- 要搜索特定用户，请使用![搜索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *按标题搜索*&#x200B;字段。
- 要筛选迁移状态列表，请选择![V形](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL 迁移状态]**。
- 要按旧登录状态筛选列表，请选择![V形](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL 旧登录]**。
- 要更改列的显示，请选择![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)并从弹出窗口中选择列。

从列表中选择一个或多个用户时，可以应用各种操作：

| 操作 | 描述 |
|---|---|
| ![迁移](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg)**[!UICONTROL 迁移]** | 您可以将一个或多个用户迁移到Enterprise ID或Adobe ID。 |
| ![日历已锁定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL 设置过期时间]** | 您可以为所选用户设置使用旧版Adobe Analytics登录的过期日期。  选择日期，以使用日历弹出窗口指定日期。 选择&#x200B;**[!UICONTROL 完成]**&#x200B;以确认过期。 |
| ![转移资产](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg)**[!UICONTROL 转移资产]** | 此操作仅在选择一个用户时可用。 如果用户拥有可转移的资产，则可以选择帐户项目（如书签、功能板等）。 选择&#x200B;**[!UICONTROL 转移]**&#x200B;以完成转移。<br/>![转移资产](assets/transfer-assets.png) |
| ![删除帐户](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除帐户]** | 将显示一个对话框，确认删除选定的帐户。 选择&#x200B;**[!UICONTROL 确定]**&#x200B;以删除帐户。 选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。 |
| ![导出到CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL 导出到CSV]** | 此操作会立即下载一个文件，其中包含所选用户的逗号分隔值列表及其详细信息（名称、迁移状态、电子邮件等）。 |

