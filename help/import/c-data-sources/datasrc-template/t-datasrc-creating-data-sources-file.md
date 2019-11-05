---
description: 导入模板文件旨在让您开始导入。
seo-description: 导入模板文件旨在让您开始导入。
seo-title: 生成导入文件模板
solution: Analytics
subtopic: 数据源
title: 生成导入文件模板
topic: 开发人员和实施
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 生成导入文件模板

导入模板文件旨在让您开始导入。

模板中定义的列不受限制。您可以根据需要任意添加其他列，只要对应所选数据处理类型的量度或定义受到支持即可。您可以在以下各节中查看每种类型有哪些受支持的量度和维度： Web [日志](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [转换](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)，完 [整的交易ID,](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)交易ID，处理访客A)。 For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

创建模板之后，您就可以下载它并导入您的数据，然后将数据上载到数据源 FTP 站点。一旦数据源服务器处理完毕，导入的数据便可用于您的Analytics报告。

数据源模板是一个 .txt 文件，可使用任何文本编辑器打开。但是，模板最简单的处理方式是使用 Microsoft Excel 或其他电子表格应用程序。模板内容会根据您在数据源激活向导中的选择而改变。

请参阅[导入文件引用](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)以了解更多详细信息。

1. 登录到 Analytics.
1. In the Suite header, select **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   步骤结果 1. 在数据源激活向导中选择模板生成选项。

   | 向导页面 | 字段 | 描述 |
   |--- |--- |--- |
   | 1 | 名称 | Analytics在数据源管理器中显示的模板名称。 |
   | 1 | 电子邮件 | 电子邮件地址，用于接收所有与使用此数据源模板相关的通知。 |
   | 1 | “相关费用”复选框 | 选中此复选框，表示您接受使用此数据源模板的相关费用。 |
   | 2 | 选择量度 | 选择要使用此数据源导入的量度。Analytics根据步骤3中选择的数据源类别和类型推荐某些指标。  若要指定其他量度，请在一个空白字段中键入其名称，然后选中相应的复选框以启用该量度。 |
   | 3 | 量度映射 | 选择分析事件以接收在向导第2页中选择的每个导入的度量。  这些应当是新的未分配事件，而之前您为其分配了与导入量度数据（将通过数据源接收）相对应的名称。如果 eVar、产品或跟踪代码变量为目标变量，并且上载的值匹配现有的捕获值，则上载的事件实际上会将量度添加到现有值。例如，您可以创建一个“脱机订单”量度，该量度的“产品”数据维度已经将“产品查看”、“结帐”和“订单”作为现有量度。 |
   | 4 | 选择数据维度 | 选择数据维度，以划分来自此数据源的导入量度。Analytics根据步骤3中选择的数据源类型推荐某些数据维度。  若要指定其他数据维度，请在一个空白字段中键入其名称，然后选中相应的复选框以启用该数据维度。 |
   | 5 | 数据维度映射 | 选择一个标准报表或 eVar，以接收在向导页面 4 中选择的每一个导入数据维度。 |

1. 在生成模板之后，将数据复制到数据源模板的相应列中，并确保符合该数据列所需的数据格式。

   步骤结果 1. 使用您选择的命名规则保存数据源文件。Adobe 建议对所有数据源文件使用统一的命名规则。使用。txt或。tsv等常用文件扩展名（或不使用任何扩展名）。

