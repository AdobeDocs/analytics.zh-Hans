---
title: 语音分析维度
description: 语音分析维度
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: 6a229439c455389b88d5fe96a0366b8888809c02
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# 语音分析维度

当您在[[!UICONTROL 应用程序报告]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)上启用[!UICONTROL 语音和聊天机器人]时，将创建以下维度（和[量度](../metrics/voice-metrics.md)）。 您可以使用[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)将它们设置为所需的字符串值。 在报表包设置中启用时，会自动创建[处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)，以将语音分析维度映射到其关联的上下文数据变量。

| 维度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 语音错误类型 | 遇到的错误类型。 | `a.voiceerrortype` |
| 语音语言 | 用户与语音应用程序交互的语言。 | `a.voicelanguage` |
| 语音意图 | 用户要运行的命令。 | `a.voiceintent` |
| 语音应用程序响应 | 语音应用程序返回给用户的响应。 | `a.voiceappresponse` |
| 语音验证 | 用户与语音应用程序交互时的已验证状态。 | `a.voiceauthentication` |
| 目标点ID | 目标点ID。 | `a.loc.poi.id` |

{style="table-layout:auto"}
