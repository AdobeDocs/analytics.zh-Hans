---
title: 数据源入门
description: 将示例数据上传到开发报表包。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 1%

---

# 数据源入门

您可以按照以下步骤轻松地将示例数据上载到开发报表包，以查看工作流的实际操作情况。 了解该过程后，您可以针对贵组织的实施扩展并定制该过程。

>[!IMPORTANT]
>
>使用开发或测试报表包按照这些步骤操作。 通过数据源上传的数据包括 **永久性**. 如果在生产报表包数据中上传了该数据，则会影响该数据。

1. 通过登录Adobe Analytics [https://experience.adobe.com](https://experience.adobe.com).
1. 导航到 **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据源]**.
1. 使用右上方的下拉菜单选择一个开发报表包。
1. 单击 **[!UICONTROL 创建]** 按钮。
1. 在 [!UICONTROL 选择类别]，选择&quot;[!UICONTROL 通用]&quot;和下 [!UICONTROL 选择类型]，选择&quot;[!UICONTROL 通用数据源（仅限概要数据）]&quot;
1. 单击&#x200B;**[!UICONTROL 激活]**。
打开显示 [!UICONTROL 数据源激活向导].
   1. 步骤1:为数据源指定名称，然后单击免责声明复选框。
   1. 步骤2:此步骤在以前版本的Adobe Analytics中有更多用法。 单击复选框，然后在其旁边的文本字段中键入任意值。
   1. 步骤3:选择要包含在数据源模板文件中的量度。 从下拉菜单中选择“Event 1”。
   1. 步骤4:此步骤在以前版本的Adobe Analytics中有更多用法。 单击复选框，然后在其旁边的文本字段中键入任意值。
   1. 步骤5:选择要包含在数据源模板文件中的维度。 从下拉菜单中选择“eVar1”。
   1. 步骤6:查看摘要，其中显示模板文件中包含的维度和量度。
   1. 步骤7:单击 **[!UICONTROL 下载]** 按钮下载数据源模板文件。 另请注意FTP站点的登录凭据，因为这些凭据很快便会使用。
1. 数据源现已创建完成；下一步是为其提供要处理的数据。 在所需的文本编辑器中打开下载的文件。
1. 模板文件包含三行；两个注释行(以“`#`“)和标题行：

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #	eVar1	event1
   Date	Evar 1	Event 1
   ```

1. 输入多行数据，用选项卡分隔每个条目。 请勿使用空格或逗号来分隔值。
   * 第一列是采用以下格式的日期： `MM/DD/YYYY/HH/mm/SS`.
   * 第二列是要包含在eVar1中的文本值。
   * 第三列是要增加事件1的金额。

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #	eVar1	event1
   Date	Evar 1	Event 1
   09/07/YYYY/11/23/00	Data source example value	3
   09/07/YYYY/15/59/00	Another data source value	18
   ```

1. 保存文件。如有需要，您可以选择为其指定其他文件名。 保存文件后，可以关闭文本编辑器。
1. 在选择的Windows资源管理器、Finder或FTP客户端中，导航到 [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. 在提示输入登录凭据时，请使用数据源创建向导的最后一步中提供的用户名和密码。 您可以通过导航到 [!UICONTROL 数据源] 单击 **[!UICONTROL FTP信息]** 。
1. 验证后，将您编辑的文件拖到已验证的FTP窗口中。
1. 在FTP窗口外的任意位置创建空文本文件。 为其指定与您上传到FTP站点的数据源文件相同的文件名，但有一个例外。 而不是 `.txt` 文件类型，为 `.fin` 文件类型。 确保操作系统设置允许您查看和更改文件类型。
1. 拖动空 `.fin` 文件到与数据源文件相同的FTP位置。 存在 `.fin` 文件可告知Adobe数据源文件已完全上传并准备引入。
1. 几分钟后，该文件会从FTP位置中消失，并在报表中可见。
1. 刷新数据源页面，并验证文件是否已成功摄取。
1. 导航到Analysis Workspace并创建一个项目。
1. 将eVar1作为维度拖动到工作区画布，将事件1作为量度。 确保工作区日期范围包含您在数据源中提供的日期。

   ![示例报表](assets/success-report.png)

## 后续步骤

[文件格式](file-format.md):了解有关创建根据您的组织定制的数据源文件的详细信息。