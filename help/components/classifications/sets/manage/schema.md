---
title: 分类集架构
description: 了解如何查看和编辑单个分类集的架构。
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: 23c9dc5cada8b1e9ad2898044a65da766a6334e9
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 4%

---

# 分类集架构

架构是您要应用于为分类集定义的关键维度的分类列表。 例如，如果您已将product定义为关键维度，并且此字段包含产品SKU，则使用该架构添加产品名称、产品颜色、产品大小等分类。

要编辑分类集的架构，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 分类集]**&#x200B;管理器中，选择要编辑其架构的分类集。
1. 在&#x200B;**[!UICONTROL 分类集：_分类集_]**对话框中，选择&#x200B;**[!UICONTROL 架构]**选项卡。 该选项卡包含以下界面元素：

   ![分类集 — 架构](assets/classification-sets-schema.png)

   * [分类列表](#classification-list)
   * [搜索](#search)
   * [操作](#actions)
   * [操作栏](#action-bar)

## 分类列表

分类列表包含以下列：

| 列 | 描述 |
|---|---|
| **[!UICONTROL 分类名称]** | 您为分类提供的名称。 |
| **[!UICONTROL 身份名称]** | 系统为分类派生的名称。 |
| **[!UICONTROL 分类者]** | 如果使用了，则为用于对此分类进行分类的查找分类集链接。 |


## 搜索

您可以在![Search](/help/assets/icons/Search.svg)中快速搜索一个或多个分类。 使用![CrossSize100](/help/assets/icons/CrossSize100.svg)清除搜索。

## 操作

以下操作可用作分类列表顶部的按钮：

| 图标 | 操作 | 描述 |
|---|---|---|
| ![添加](/help/assets/icons/Add.svg) | **[!UICONTROL 加]** | [向列表中添加分类](#add)。 |
| ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) | **[!UICONTROL 上传]** | [上传JSON、CSV、TSV或TAB文件](#upload)。 |
| ![下载](/help/assets/icons/Download.svg) | **[!UICONTROL 下载]** | [下载分类数据](#download)。 |
| ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) | **[!UICONTROL 模板]** | [下载分类数据的模板](#template)。 |
| ![历史记录](/help/assets/icons/History.svg) | **[!UICONTROL 作业历史记录]** | 显示针对所选分类集筛选的[分类集作业管理器](/help/components/classifications/sets/job-manager.md)。 |
| ![齿轮](/help/assets/icons/Gear.svg) | **[!UICONTROL 自动化]** | [通过使用云位置自动摄取分类数据](#automate)。 |


### 加

要添加新分类，请选择![添加](/help/assets/icons/Add.svg) **[!UICONTROL 添加]**。

![分类集 — 将分类添加到架构](assets/classification-sets-schema-add-classification.png)

在&#x200B;**[!UICONTROL 为&#x200B;_分类集_]**添加新分类对话框中，输入&#x200B;**[!UICONTROL 分类名称]**并选择&#x200B;**[!UICONTROL 添加]**。 分类即添加到列表中。



### 上传

要将分类数据导入分类的架构，请选择![UploadToCloud](/help/assets/icons/UploadToCloud.svg) **[!UICONTROL 上传]**。


![分类集 — 架构上载文件](assets/classification-sets-schema-upload-file.png)

1. 在&#x200B;**[!UICONTROL 添加新分类]**&#x200B;对话框中：

   * 将包含分类数据的文件拖放到&#x200B;**[!UICONTROL 将拖放到此处]**。
   * 选择&#x200B;**[!UICONTROL 浏览]**&#x200B;并从您的计算机或网络中选择文件。

   您看到该文件内容的&#x200B;**[!UICONTROL 架构预览]**。 预览显示来自文件的数据列。 要调整列大小，请选择![V形向下大小300](/help/assets/icons2/ChevronDownSize300.svg)，然后选择&#x200B;**[!UICONTROL 调整列大小]**。 出现一个句柄，允许您调整列的大小。

   当列的分类集中未定义分类时，将显示警报![警报](/help/assets/icons/Alert.svg)。 警报说明现有分类架构集中不存在分类，并且将在导入时创建。

1. 选择&#x200B;**[!UICONTROL 发生冲突时覆盖数据？]**（如果要使用新导入的内容覆盖当前分类数据）。 例如：

   | | 键 | 当前产品颜色 | 导入文件 | 新产品颜色 |
   |---|---|---|---|---|
   | ![SelectBox](/help/assets/icons/SelectBox.svg) **[!UICONTROL 在冲突时覆盖数据？]** | 1234 | 绿色 | 蓝色 | 蓝色 |
   | ![方形](/help/assets/icons2/Square.svg) **[!UICONTROL 在冲突时覆盖数据？]** | 1234 | 绿色 | 蓝色 | 绿色 |

1. 选择&#x200B;**[!UICONTROL 应用]**。如果列不存在于现有架构集中作为分类，则会显示警报。 当您确认上传时，这些列将作为新分类添加。

   ![分类集 — 上载分类警报](assets/classification-sets-schema-upload-file-preview-alert.png)

   选择&#x200B;**[!UICONTROL 确认上传]**&#x200B;以确认上传。 选择&#x200B;**[!UICONTROL 取消上传]**&#x200B;以取消上传。


### 下载

要下载分类数据，请选择![下载](/help/assets/icons/Download.svg) **[!UICONTROL 下载]**。

![分类集 — 架构下载分类数据](assets/classification-sets-schema-download-file.png)

在&#x200B;**[!UICONTROL 下载&#x200B;_分类集_]**的数据对话框中：

1. 输入要下载的&#x200B;**[!UICONTROL 行数]**。 例如：`10000`。
1. 要选择要下载分类数据行的期间，请为&#x200B;**[!UICONTROL 下载接收行数（介于]**&#x200B;之间）输入开始和结束数据。 或者使用![日历](/help/assets/icons/Calendar.svg)使用日历弹出窗口选择时段。
1. 若要选择要返回的数据，请从&#x200B;**[!UICONTROL 返回的数据]**&#x200B;中选择一个选项。

   * **[!UICONTROL 所有值]**&#x200B;返回当前分类数据的所有值。
   * **[!UICONTROL 任何为空]**&#x200B;的列都将返回一个包含现有分类数据的键值的列。 对于不存在值的分类数据，和没有值的列。
   * **[!UICONTROL 所有列为空]**&#x200B;返回键列，该键列包含现有分类数据的值。 和分类数据没有值的列。
1. 要选择下载的分类数据的[文件格式](/help/components/classifications/sets/data-files.md#general-file-requirements)，请从&#x200B;**[!UICONTROL 文件格式]**&#x200B;下拉菜单中选择一个选项。 选项如下：

   * **[!UICONTROL JSON]**。
   * **[!UICONTROL 逗号分隔值]** (CSV)。
   * **[!UICONTROL Excel选项卡分隔值]**（TSV或TAB）。

1. 要选择下载文件时要使用的[文件编码](/help/components/classifications/sets/data-files.md#general-file-requirements)，请从“文件编码”下拉菜单中选择一个选项。 选项如下：

   * **[!UICONTROL UTF-8]**。
   * **[!UICONTROL 拉丁语–1]**。


1. 选择&#x200B;**[!UICONTROL 下载]**&#x200B;以下载分类数据。 您可以在浏览器的默认下载目录中找到下载的文件，该文件标题为<code><i>分类集</i>。<i>json</i>|<i>csv</i>|<i>tsv</i></code>。如果文件已存在，则序列号为<code>(<i>x</i>)</code> 会添加到文件名中。<br/>如果您指定了不返回任何数据的选项，则会看到&#x200B;**[!UICONTROL 通知]**&#x200B;对话框，通知您更改日期范围和返回数据的选项。


### 模板

要下载分类数据的模板，请选择![DocumentFragment](/help/assets/icons/DocumentFragment.svg) **[!UICONTROL Template]**。

![分类集架构 — 下载模板](assets/classification-sets-schema-download-template.png)

在&#x200B;**[!UICONTROL 分类集&#x200B;_的_]**下载模板对话框中：

1. 要选择下载的分类数据的[文件格式](/help/components/classifications/sets/data-files.md#general-file-requirements)，请从&#x200B;**[!UICONTROL 文件格式]**&#x200B;下拉菜单中选择一个选项。 选项如下：

   * **[!UICONTROL 逗号分隔值]**。
   * **[!UICONTROL Excel选项卡分隔值]**。

1. 要选择下载文件时要使用的[文件编码](/help/components/classifications/sets/data-files.md#general-file-requirements)，请从“文件编码”下拉菜单中选择一个选项。 选项如下：

   * **[!UICONTROL UTF-8]**。
   * **[!UICONTROL 拉丁语–1]**。

1. 选择&#x200B;**[!UICONTROL 下载]**&#x200B;以下载分类数据模板。 您可以在浏览器的默认下载目录中找到下载的文件，其标题为<code><i>分类集</i>。<i>csv</i>|<i>tsv</i></code>。如果文件已存在，则序列号为<code>(<i>x</i>)</code> 会添加到文件名中。


### 自动化

要自动摄取分类，请选择![齿轮](/help/assets/icons/Gear.svg)**[!UICONTROL 自动]**。

![分类集架构 — 自动化](assets/classification-sets-schema-automate.png)

在&#x200B;**[!UICONTROL 关联/更新&#x200B;_分类集_]**的引入位置对话框中：

1. 若要选择云位置，请从&#x200B;**[!UICONTROL 位置帐户]**&#x200B;中选择一个选项。 只显示允许导入分类数据[的受支持帐户类型的](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)位置帐户。 要创建新帐户，请选择&#x200B;**[!UICONTROL 新建帐户]**。
1. 若要选择位置，请从&#x200B;**[!UICONTROL 位置]**&#x200B;中选择一个选项。 只显示用于导入分类数据的所选帐户类型的位置。 要创建新位置，请选择&#x200B;**[!UICONTROL 新建位置]**。
1. 若要选择分隔符，请从&#x200B;**[!UICONTROL 列表分隔符]**&#x200B;中选择一个选项。 选项包括：
   * **[!UICONTROL 逗号，]**
   * **[!UICONTROL 分号；]**
   * **[!UICONTROL 冒号：]**
   * **[!UICONTROL 垂直条 |]**
   * **[!UICONTROL 共享空间]**
   * **[!UICONTROL 选项卡]**
1. 要在下载文件时选择[文件编码](/help/components/classifications/sets/data-files.md#general-file-requirements)，请从&#x200B;**[!UICONTROL 文件编码]**&#x200B;下拉菜单中选择一个选项。 选项如下：

   * **[!UICONTROL UTF-8]**。
   * **[!UICONTROL 拉丁语–1]**。

1. 要通知用户已完成引入作业，请输入以逗号分隔的电子邮件地址，以便&#x200B;**[!UICONTROL 在引入作业完成时通知电子邮件（以逗号分隔）]**。
1. 选择&#x200B;**[!UICONTROL 验证]**。 已验证与云位置的连接。
1. 如果验证成功，您会看到一则显示![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 位置验证成功的Toast消息。 已验证与云存储的连接。]**<br/>如果已创建与云连接的连接，请选择**[!UICONTROL &#x200B;保存&#x200B;]**。 否则，请选择**[!UICONTROL &#x200B;更新&#x200B;]**。 或者选择**[!UICONTROL &#x200B;取消&#x200B;]**以取消云位置的配置。


## 操作栏

操作栏显示可用于所选分类集的操作。 可用选项包括：

| 图标 | 操作 | 描述 |
|---|---|---|
| ![浏览](/help/assets/icons/Browse.svg) | **[!UICONTROL 添加查找]** | 添加分类集作为查询（子分类）。<br/>在&#x200B;**[!UICONTROL 附加查找]**&#x200B;表中： <ol><li>从&#x200B;**[!UICONTROL 分类名称]**&#x200B;下拉菜单中选择查找分类。</li><li>选择&#x200B;**[!UICONTROL 添加]**。</li></ol>查找分类已添加到该分类中，并使用内部ID列在&#x200B;**[!UICONTROL 分类者]**&#x200B;列中。 |
| ![删除圆圈](/help/assets/icons/RemoveCircle.svg) | **[!UICONTROL 删除查找]** | 删除分类集作为查找。 若要从分类中永久删除查找，请在&#x200B;**[!UICONTROL 从&#x200B;_分类_删除分类集&#x200B;_确认对话框中，选择_]**删除&#x200B;**[!UICONTROL 。]** |
| ![重命名](/help/assets/icons/Rename.svg) | **[!UICONTROL 重命名]** | 重命名分类。 在&#x200B;**[!UICONTROL 重命名： _分类_]**对话框中，输入新名称并选择&#x200B;**[!UICONTROL 重命名]**。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除分类集。 出现&#x200B;**[!UICONTROL 删除&#x200B;_分类_]**对话框。 选择&#x200B;**[!UICONTROL 删除]**以删除分类集。 |


<!--

View currently configured classification dimensions for this classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Click the desired classification set name > **[!UICONTROL Schema]**

![classification set schema UI](../../assets/classification-set-schema.png)

The following buttons are available:


* **[!UICONTROL Upload]**: Manually upload classification data for a classification dimensions. `JSON`, `CSV`, `TSV`, and `TAB` files are supported. Uploading a valid file shows a table preview of data to classify.
  * **[!UICONTROL File encoding]**: Select the correct file encoding using this drop-down. Valid options include [!UICONTROL UTF-8] and [!UICONTROL Latin1].
  * **[!UICONTROL List delimiter]**: Select the correct list delimiter. If using a downloaded file or template file, make sure that the [!UICONTROL List delimiter] here matches the [!UICONTROL List delimiter] when the file was downloaded.
  * **[!UICONTROL Apply]**: Save the uploaded classification data to the classification set.

  ![Classification set upload](../../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: Download key values and their classification columns.
  * **[!UICONTROL Rows]**: The maximum number of rows to include in the download file.
  * **[!UICONTROL Download rows received between]**: A calendar date picker that allows you to filter key values by when they appear in reporting. If a key value was not collected in this date range, it does not appear in the downloaded file.
  * **[!UICONTROL Data returned]**: A drop-down list that lets you filter key values included in the downloaded file based on their associated classification data.
    * **[!UICONTROL All classified values]**: Includes rows where classification data is included in at least one column.
    * **[!UICONTROL All unclassified values]**: Includes rows where classification data is missing in at least one column.
  * **[!UICONTROL File format]**: A drop-down list that determines the file format that the download file is in. Options include [!UICONTROL JSON], [!UICONTROL Comma separated values], and [!UICONTROL Excel tab separated values].
  * **[!UICONTROL File encoding]**: A drop-down list that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.

  ![Classification set download](../../assets/classification-set-download.png)

* **[!UICONTROL Template]**: Download a template file. This file is similar to the [!UICONTROL Download] button, except it does not contain any classification data or key values.
  * **[!UICONTROL File format]**: A drop-down list that determines the file format that the template file is in. Options include [!UICONTROL Comma separated values], and [!UICONTROL Excel tab separated values].
  * **[!UICONTROL File encoding]**: A drop-down list that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.
  * **[!UICONTROL List delimiters]**: A drop-down list that determines the list delimiter separating classification columns on each row.

  ![Classification set template](../../assets/classification-set-template.png)

* **[!UICONTROL Job history]**: A shortcut link that takes you to the [Job manager](../job-manager.md), showing jobs only for this classification set.
* **[!UICONTROL Automate]**: Automatically ingest data from external storage locations.
  * **[!UICONTROL Location account]**: A drop-down list showing existing location accounts that your organization has configured. If your organization hasn't already configured a location account, you can configure one by selecting [!UICONTROL **Create a new account**].
    
    For information about configuring the location account, see [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

  * **[!UICONTROL Location]**: A drop-down list showing existing locations that your organization has configured. If your organization hasn't already configured a location, you can configure one by selecting [!UICONTROL **Create a new location**]. 

    For information about configuring a location, see [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md). 

  * **[!UICONTROL Delimiter]**: The column delimiter for uploaded files. Options include [!UICONTROL Comma], [!UICONTROL Semicolon], [!UICONTROL Colon], [!UICONTROL Vertical bar], [!UICONTROL Space], [!UICONTROL Forward slash], [!UICONTROL Backward slash], [!UICONTROL Dash], or [!UICONTROL Underscore].

  * **[!UICONTROL Encoding]**: A drop-down list that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.

The following actions are available only after selecting a classification.

* **Add lookup**: A lookup table is a classification of a classification. It is metadata about a classification value, rather than the variable itself. For example, the Product variable might have a classification of "color code". A lookup table of "color name" might be attached to "color code" to explain what the colors are.

  ![Attach lookup table](../../assets/lookup.png)

* **Rename**: Lets you rename the classification.

* **Delete**: Lets you delete the classification.
-->