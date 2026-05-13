---
description: 您可以使用浏览器导入（上传）分类数据。 此方法仅限将分类数据上传到单个报表包。
title: 浏览器导入
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
TQID: https://experienceleague.adobe.com/iFVW-d9C12dj6TXnUlA3-zVF0oBAWpJwg1JK8LqzF-s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 52%

---

# 浏览器导入（旧版）

{{classification-importer-deprecation}}

您可以使用浏览器导入（上传）分类数据。 此方法仅限将分类数据上传到单个报表包。

## 浏览器导入 {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

您可以使用浏览器导入（上传）分类数据。 此方法仅限将分类数据上传到单个报表包。

**[!UICONTROL 管理员]** > **[!UICONTROL 分类导入器]**

## 分类浏览器导入 — 字段描述 {#section_F628C47081DA4026A4D30E3D3454B1DA}

| 元素 | 描述 |
| --- | --- |
| 选择报表包 | 要导入分类数据的报表包。 导入数据文件必须与报表包中数据集的格式匹配。 |
| 要分类的数据集 | 用于接收分类的数据集。 下拉列表包含报表包中所有为分类配置的报告。 |
| 选择要导入的文件 | 让您浏览以查找要上传的导入数据文件。  注意：上传文件大小限制为 1 MB。 |
| 发生冲突时覆盖数据 | 自动覆盖与导入的数据冲突的现有数据。<br>**重要提示**：此选项不适用于启用新分类架构的报表包。 |
| 导入完成后自动下载分类文件 | 自动下载以制表符分隔的文件，该文件代表具有新上传的分类数据的数据集。 如果导入操作创建任何唯一ID，或者发生任何错误，Adobe会自动为您生成此文件。<br>**重要信息**：此选项不适用于启用新分类架构的报表包。 |


## 通过浏览器导入分类 {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. 单击&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 分类导入器]**。
1. 单击&#x200B;**[!UICONTROL 导入文件]**。
1. 配置&#x200B;**[!UICONTROL 浏览器导入]**&#x200B;字段。
1. 单击&#x200B;**[!UICONTROL 导入文件]**。
1. 查看状态窗口以了解处理消息。
1. （视情况而定）如果您选择了&#x200B;**[!UICONTROL 上传完成后自动下载分类文件]**，请指定希望在处理完成时用于存储所生成文件的位置。 请注意，此选项不适用于启用新分类架构的报表包。

>成功的导入会立即在导出中显示相应的更改。 但是，使用浏览器导入时，报表中的数据更改最多需要4小时，使用FTP导入时，的数据更改最多需要24小时。
