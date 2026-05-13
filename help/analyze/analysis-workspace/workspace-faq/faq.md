---
description: 获取有关 Analysis Workspace 的常见问题解答。
title: 常见问题解答
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 88%

---

# 常见问题解答

+++使用 Analysis Workspace 的先决条件是什么？
[使用 Adobe Analytics 扩展将数据发送到 Adobe Analytics](/help/implement/launch/validate-publish-prod.md)：使用 Analysis Workspace 需要有效的实施。 在使用这款工具之前，请确保您的组织向 Adobe 发送数据。 其他实施（如旧版手动实施）也可以正常工作。
+++

+++管理和访问 Analysis Workspace 有哪些要求？
请参阅[管理要求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。
+++

+++使用 Analysis Workspace 是否会影响数据收集？
由于 Analysis Workspace 是一款报告工具，因此不会对数据收集产生任何影响。 您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。 将不同的维度和量度组合拖动到 Workspace 项目中，可查看相应的效果。 如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。 此外，您还可以通过单击左上角菜单中的&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 新建]**&#x200B;来重头开始创建。
+++

+++一个 Analysis Workspace 项目可以显示多少个报表包？
您现在可以在 Analysis Workspace 中使用[多个报表包](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md)的数据创建项目。
+++

+++如何实施Analysis Workspace？
无需特殊实施。 Analysis Workspace适用于具有Analytics Standard或Premium的所有公司。 但是，内容（如报告包和项目组件）的标准权限在此适用，并可用于组织和共享项目。 请参阅[管理和访问要求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。
+++

+++我能否使用Analysis Workspace for Data Warehouse？
不建议使用Analysis Workspace来批量导出数据。 它是一个创建类似功能板分析项目的可视化图表工作区。
+++

+++如何优化 Analysis Workspace 的性能？

请参阅[优化性能](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。

+++

+++数据如何进入您的 Analysis Workspace 项目？

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [数据输入 Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"}以获取演示视频。

+++

+++如何跟踪 Workspace 使用情况？

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [日志跟踪](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"} 以获取演示视频。

+++

+++当我将量度拖动到上面时，显示“数据无效”。 如何解决这个问题？

无效数据意味着 Adobe 无法通过报告中使用的维度和量度组合返回数据。 例如，两个彼此堆叠的量度不能作为数据返回，因为无法以这种堆叠方式显示这两个量度。 相反，应将两个量度并排放置。

+++

+++当我将量度拖动到上面时，看不到任何实际数据 - 只有零。 如何解决此问题？

如果您成功创建了工作区报告，但报告中没有数据，则可以检查以下几项内容：

* 仔细检查报告包，并确保报告包中已填充数据。
* 如果在报告中应用了区段，区段标准可能与所有数据不匹配。 请尝试移除区段或调整区段定义。
* 检查右上角的日期范围，并确保它已设置为预期的值。
* 导航到您的网站，然后使用 [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 验证正在收集的数据。


+++

+++作为只读用户，我可以在 Analysis Workspace 中执行哪些操作？
如果项目以只读方式共享，所有编辑功能和特点都被完全禁用，接收者只能更改下拉菜单，按一种预定义的方式在面板上应用过滤器。
+++
