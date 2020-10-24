---
description: 导入模板文件旨在让您开始导入。
subtopic: Data sources
title: 生成导入文件模板
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '596'
ht-degree: 100%

---


# 生成导入文件模板

导入模板文件旨在让您开始导入。

模板中定义的列不受限制。您可以根据需要任意添加其他列，只要对应所选数据处理类型的量度或定义受到支持即可。您可以在以下各节中查看每种类型有哪些受支持的量度和维度：[网络日志](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)、[流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)、[转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)、[交易 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)、[访客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)、[完全处理](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)。例如，对于流量数据类型，您可以为[流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)中列出的任何量度或维度添加一列。

创建模板之后，您就可以下载它并导入您的数据，然后将数据上载到数据源 FTP 站点。在经数据源服务器处理之后，导入的数据即可用于您的 Analytics 报表。

数据源模板是一个 .txt 文件，可使用任何文本编辑器打开。但是，模板最简单的处理方式是使用 Microsoft Excel 或其他电子表格应用程序。模板内容会根据您在数据源激活向导中的选择而改变。

请参阅[导入文件引用](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)以了解更多详细信息。

1. 登录到 Analytics。
1.  在包标题中，选择&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL Data Sources]**。
1. 在 **[!UICONTROL 数据源创建]**&#x200B;选项卡中，选择模板类别和类型。
1. 查看激活指令/信息，然后点击&#x200B;**[!UICONTROL 激活]**。

   步骤结果 1. 在数据源激活向导中选择模板生成选项。

   | 向导页面 | 字段 | 描述 |
   |--- |--- |--- |
   | 1 | 名称 | Analytics 在数据源管理器中显示的模板名称。 |
   | 1 | 电子邮件 | 电子邮件地址，用于接收所有与使用此数据源模板相关的通知。 |
   | 1 | “相关费用”复选框 | 选中此复选框，即表示您接受在使用此数据源模板时产生的相关费用。 |
   | 2 | 选择量度 | 选择要使用此数据源导入的量度。Analytics 建议某些特定量度应基于在步骤 3 中选择的数据源类别和类型。若要指定其他量度，请在一个空白字段中键入其名称，然后选中相应的复选框以启用该量度。 |
   | 3 | 量度映射 | 选择一个 Analytics 事件，以接收在向导页面 2 中选择的每一个导入量度。这些应当是新的未分配事件，而之前您为其分配了与导入量度数据（将通过数据源接收）相对应的名称。如果 eVar、产品或跟踪代码变量为目标变量，并且上载的值匹配现有的捕获值，则上载的事件实际上会将量度添加到现有值。例如，您可以创建一个具有产品数据维度的“离线订购”量度，该产品数据维度中已有产品查看、结账和订购作为其现有量度。 |
   | 4 | 选择数据维度 | 选择数据维度，以划分来自此数据源的导入量度。Analytics 建议某些特定数据维度应基于在步骤 3 中选择的数据源类型。若要指定其他数据维度，请在一个空白字段中键入其名称，然后选中相应的复选框以启用该数据维度。 |
   | 5 | 数据维度映射 | 选择一个标准报表或 eVar，以接收在向导页面 4 中选择的每一个导入数据维度。 |

1. 在生成模板之后，将数据复制到数据源模板的相应列中，并确保符合该数据列所需的数据格式。

   步骤结果 1. 使用您选择的命名规则保存数据源文件。Adobe 建议对所有数据源文件使用统一的命名规则。使用常见的文件扩展名，如 .txt 或 .tsv（或者不使用任何扩展名）。

