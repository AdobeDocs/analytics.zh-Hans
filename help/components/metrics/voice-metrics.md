---
title: 语音分析量度
description: 语音分析量度
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 102
ht-degree: 21%

---

# 语音分析量度

当您在[[!UICONTROL 应用程序报表]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md)上启用[!UICONTROL 语音和聊天机器人]时，将创建以下量度（和[维度](../dimensions/voice-dimensions.md)）。 您可以使用[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)将这些变量设置为值`1`（如果适用的话，该值会更大）。 在报表包设置中启用时，会自动创建[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，以将语音分析量度映射到其关联的上下文数据变量。

| 量度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 语音言语 | 向语音助手发出命令时触发。 | `a.voiceutterances` |
| 语音结束会话 | 语音应用程序关闭时触发。 | `a.voiceendsession` |
| 语音错误 | 语音应用程序遇到错误时触发。 | `a.voiceerror` |

{style="table-layout:auto"}
