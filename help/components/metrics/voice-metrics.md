---
title: 语音分析量度
description: 语音分析量度
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: 6a229439c455389b88d5fe96a0366b8888809c02
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# 语音分析量度

当您在[[!UICONTROL 应用程序报表]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)上启用[!UICONTROL 语音和聊天机器人]时，将创建以下量度（和[维度](../dimensions/voice-dimensions.md)）。 您可以使用[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)将这些变量设置为值`1`（如果适用的话，该值会更大）。 在报表包设置中启用时，会自动创建[处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)，以将语音分析量度映射到其关联的上下文数据变量。

| 量度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 语音言语 | 向语音助手发出命令时触发。 | `a.voiceutterances` |
| 语音结束会话 | 语音应用程序关闭时触发。 | `a.voiceendsession` |
| 语音错误 | 语音应用程序遇到错误时触发。 | `a.voiceerror` |

{style="table-layout:auto"}
