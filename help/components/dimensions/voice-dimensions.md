---
title: 语音分析维度
description: 语音分析维度
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 133
ht-degree: 16%

---

# 语音分析维度

当您在[[!UICONTROL 应用程序报告]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)上启用[!UICONTROL 语音和聊天机器人]时，将创建以下维度（和[量度](../metrics/voice-metrics.md)）。 您可以使用[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)将它们设置为所需的字符串值。 在报表包设置中启用时，会自动创建[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，以将语音分析维度映射到其关联的上下文数据变量。

| 维度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 语音错误类型 | 遇到的错误类型。 | `a.voiceerrortype` |
| 语音语言 | 用户与语音应用程序交互的语言。 | `a.voicelanguage` |
| 语音意图 | 用户要运行的命令。 | `a.voiceintent` |
| 语音应用程序响应 | 语音应用程序返回给用户的响应。 | `a.voiceappresponse` |
| 语音身份验证 | 用户与语音应用程序交互时的已验证状态。 | `a.voiceauthentication` |
| 目标点 ID | 目标点ID。 | `a.loc.poi.id` |

{style="table-layout:auto"}
