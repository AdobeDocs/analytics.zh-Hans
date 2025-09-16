---
description: 获取有关 Analysis Workspace 的常见问题解答。
title: 常见问题解答
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# 常见问题解答

+++使用 Analysis Workspace 的先决条件是什么？
[使用 Adobe Analytics 扩展将数据发送到 Adobe Analytics](/help/implement/launch/validate-publish-prod.md)：使用 Analysis Workspace 需要有效的实施。在使用这款工具之前，请确保您的组织向 Adobe 发送数据。 其他实施（如旧版手动实施）也可以正常工作。
+++

+++管理和访问 Analysis Workspace 有哪些要求？
请参阅[管理要求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。
+++

+++使用 Analysis Workspace 是否会影响数据收集？
由于 Analysis Workspace 是一款报告工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和量度组合拖动到工作区项目中，可查看相应的效果。如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。此外，您还可以通过单击左上角菜单中的&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 新建]**&#x200B;来重头开始创建。
+++

+++一个 Analysis Workspace 项目可以显示多少个报表包？
您现在可以在 Analysis Workspace 中使用[多个报表包](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md)的数据创建项目。
+++

+++如何实施 Analysis Workspace？
无需特殊实施。Analysis Workspace 可向所有使用 Analytics Standard 或 Premium 的公司提供。但是，内容（如报告包和项目组件）的标准权限在此适用，并可用于组织和共享项目。请参阅[管理和访问要求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。
+++

+++我可以将 Analysis Workspace 用于 Data Warehouse 吗？
不建议将 Analysis Workspace 用于批量数据导出。它是一个创建类似功能板分析项目的可视化图表工作区。
+++

+++如何优化 Analysis Workspace 的性能？

请参阅[优化性能](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。

+++

+++数据如何进入您的 Analysis Workspace 项目？

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [数据输入 Analysis Workspace](https://video.tv.adobe.com/v/33229?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取演示视频。

+++

+++如何跟踪 Workspace 使用情况？

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [日志跟踪](https://video.tv.adobe.com/v/29768?quality=12&learn=on){target="_blank"} 以获取演示视频。

+++

+++当我将量度拖动到上面时，显示“数据无效”。如何解决这个问题？

无效数据意味着 Adobe 无法通过报告中使用的维度和量度组合返回数据。例如，两个彼此堆叠的量度不能作为数据返回，因为无法以这种堆叠方式显示这两个量度。相反，应将两个量度并排放置。

+++

+++当我将量度拖动到上面时，看不到任何实际数据 - 只有零。如何解决此问题？

如果您成功创建了工作区报告，但报告中没有数据，则可以检查以下几项内容：

* 仔细检查报告包，并确保报告包中已填充数据。
* 如果在报告中应用了区段，区段标准可能与所有数据不匹配。请尝试移除区段或调整区段定义。
* 检查右上角的日期范围，并确保它已设置为预期的值。
* 导航到您的网站，然后使用 [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans) 验证正在收集的数据。


+++

+++作为只读用户，我可以在 Analysis Workspace 中执行哪些操作？
如果项目以只读方式共享，所有编辑功能和特点都被完全禁用，接收者只能更改下拉菜单，按一种预定义的方式在面板上应用过滤器。
+++
