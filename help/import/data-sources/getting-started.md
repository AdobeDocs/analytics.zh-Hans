---
title: 数据源快速入门
description: 将示例数据上传到开发报表包。
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 1%

---

# 数据源快速入门

您可以按照以下步骤轻松将示例数据上传到开发报表包中，以查看工作流的运行情况。 了解该流程后，您可以针对贵组织的实施进行扩展和定制。

>[!IMPORTANT]
>
>使用开发或测试报表包执行以下步骤。 通过数据源上传的数据包括 **永久**. 如果上传到那里，将会影响生产报表包数据。

1. 通过以下方式登录Adobe Analytics [https://experience.adobe.com](https://experience.adobe.com).
1. 导航到 **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据源]**.
1. 使用右上方的下拉列表选择开发报表包。
1. 单击 **[!UICONTROL 创建]** 按钮进行修改。
1. 下 [!UICONTROL 选择类别]，选择“[!UICONTROL 通用]“”，和下 [!UICONTROL 选择类型]，选择“[!UICONTROL 通用数据源（仅限概要数据）]“。
1. 单击&#x200B;**[!UICONTROL 激活]**。
随即会打开一个弹出窗口，显示 [!UICONTROL 数据源激活向导].
   1. 步骤1：为数据源命名，然后单击免责声明复选框。
   1. 第2步：此步骤在Adobe Analytics的早期版本中有更多用处。 单击复选框，然后在旁边的文本字段中键入任意值。
   1. 步骤3：选择要包含在数据源模板文件中的量度。 从下拉列表中选择“事件1”。
   1. 步骤4：此步骤在Adobe Analytics的早期版本中有更多用处。 单击复选框，然后在旁边的文本字段中键入任意值。
   1. 步骤5：选择要包含在数据源模板文件中的维度。 从下拉列表中选择“eVar1”。
   1. 步骤6：查看摘要，其中显示了模板文件中包含的维度和量度。
   1. 步骤7：单击 **[!UICONTROL 下载]** 按钮以下载数据源模板文件。 另请注意FTP站点的登录凭据，因为它们很快就会使用。
1. 数据源现已创建；下一步是为它提供要处理的数据。 在所需的文本编辑器中打开下载的文件。
1. 模板文件包含三行；两行注释（以“”开头）`#`“)，并且标头行：

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. 输入多行数据，每个条目之间用制表符分隔。 请勿使用空格或逗号来分隔值。
   * 第一列是以下格式的日期： `MM/DD/YYYY/HH/mm/SS`.
   * 第二列是您要包含在eVar1中的文本值。
   * 第三列是您希望增加事件1的数量。

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. 保存文件。如果需要，您可以选择为其指定不同的文件名。 保存文件后，可以关闭文本编辑器。
1. 在所选Windows资源管理器、Finder或FTP客户端中，导航到 [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. 在系统提示输入登录凭据时，请使用数据源创建向导的最后一步中提供的用户名和密码。 您可以通过导航到 [!UICONTROL 数据源] 并单击 **[!UICONTROL FTP信息]** ，位于您创建的数据源旁边。
1. 完成身份验证后，将编辑的文件拖到经过身份验证的FTP窗口中。
1. 在FTP窗口之外的任何位置创建一个空文本文件。 为其指定与您上传到FTP站点的数据源文件相同的文件名，但有一个例外。 而不是 `.txt` 文件类型，为其赋值 `.fin` 文件类型。 确保您的操作系统设置允许您查看和更改文件类型。
1. 拖动空的 `.fin` 文件到与数据源文件相同的FTP位置。 存在 `.fin` file告知Adobe数据源文件已完全上传并准备好被摄取。
1. 几分钟后，文件从FTP位置消失，并在报表中可见。
1. 刷新“数据源”页面并验证文件是否已成功摄取。
1. 导航到Analysis Workspace并创建项目。
1. 将eVar1作为维度拖动到工作区画布，将“事件1”作为指标拖动。 确保工作区日期范围包含您在数据源中提供的日期。

   ![示例报告](assets/success-report.png)

## 后续步骤

[文件格式](file-format.md)：了解有关创建为您的组织量身定制的数据源文件的详细信息。
