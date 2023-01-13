---
description: “数据管理的隐私标签”对话框概述了报表包的隐私标签和命名空间。 您也可以从此处将设置导出到.csv文件。
title: 查看/管理用于数据管理的隐私标签
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: f719691800e4560aeb822825170a15ead5044e7b
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 44%

---

# 查看/管理用于数据管理的隐私标签

>[!NOTE]
>
>此更新的UI当前处于有限测试中。

的 **[!UICONTROL 数据管理的隐私标签]** 对话框提供报表包隐私标签和命名空间的概述。 您也可以从此处将设置导出到.csv文件。

## 查看隐私标签 {#view-privacy}

1. 登录到 Adobe Experience Cloud。
1. 导航到  **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据配置和收集]** > **[!UICONTROL 数据管理]**.

   >[!NOTE]
   >
   >如果您没有看到此菜单项，则需要将您添加到 [Admin Console 中的产品配置文件](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)，并为您提供对此功能的各种权限。

1. 选择右上角的要查看或管理其隐私标签的报表包。

   ![](assets/privacy_labeling.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 组件名称]** | 此列列出了属于此报表包的所有组件（维度、量度）。 |
| **[!UICONTROL 标识]** | 身份数据“I”标签用于对可识别或联系特定人员的数据进行分类。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#identity-data-labels) |
| **[!UICONTROL 灵敏度]** | 敏感数据“S”标签用于对诸如地理数据之类的敏感数据进行分类。未来，会引入其他敏感数据标签，用于识别其他类型的敏感信息。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#sensitive-data-labels) |
| **[!UICONTROL GDPR访问]** | 通过数据治理标签，用户可将反映与隐私相关的考虑因素和合同条件的数据分类，以符合法规和公司政策。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-access-labels) |
| **[!UICONTROL GDPR删除]** | 只有当字段中包含的值能够将命中项与该数据主体进行关联时（即，可用来识别数据主体），这些字段才需要使用删除标签。不需要删除其他个人信息（收藏夹、浏览/购买历史、健康状况等），因为这会切断与数据主体的关联。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-delete-labels) |
| **[!UICONTROL 命名空间]** | 在为变量设置 ID-DEVICE 或 ID-PERSON 标签时，系统会提示您提供一个命名空间。您可以使用先前已定义的命名空间或者定义一个新的命名空间。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#section_F0A47AF8DA384A26BD56032D0ABFD2D7) |
| **[!UICONTROL 类别]** | 指组件类型，如标准组件、转化变量等。 |

{style=&quot;table-layout:auto&quot;}

## 将隐私标签复制到报表包  {#copy-to-rs}

如果要将相同的DULE/数据隐私设置应用于多个报表包，请执行以下步骤：

1. 选择要复制的变量。 请注意，您一次只能复制一个变量的标签。
1. 单击 **[!UICONTROL 复制到报表包]** “数据管理”对话框的底部。

   ![复制到报表包](assets/copy_to_reportsuite.png)

1. 生成的屏幕显示变量名称、您尝试复制的当前应用的标签、报表包及其ID，以及目标报表包中的设置是否匹配。

   ![将标签复制到报表包](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >请记住，您选择的所有报告包都必须映射到您的 Experience Cloud 组织。

   将一个变量或一组变量的标签复制到不同的报告包时，复制的标签会转到目标报告包中相应位置的变量中。对于标准组件、列表变量和成功事件，标签将复制到 **相同名称** 中。

   但是，对于转化变量(eVar)和流量Dimension(prop)，复制的变量将包含 **相同数字** 中。 例如，eVar12 将被复制到所有目标报告包的 eVar12 中。在确定复制的目标时，会忽略这些变量的名称。如果相应的变量未在目标报告包中启用，则针对该变量的标签复制将会失败。

   在复制为变量定义的分类标签时，标签将被复制到目标报表包中相应变量(如eVar7到eVar7)的分类中，该变量的名称与要复制的分类的名称相同。 否则，该分类标签的复制将会失败。

1. 选中设置匹配的一个或多个报表包旁边的复选框。
1. 单击&#x200B;**[!UICONTROL 应用]**。

   在应用标签后，会显示状态消息。 状态消息将包含复制失败的所有目标变量或分类及其报告包的名称。

   >[!IMPORTANT]
   >
   >您应该经常检查目标报告包，以确保正确复制标签。对于具有 ID 或 DEL 标签的变量来说，这一点尤为重要。

## 导出到.csv文件

您可以下载一个CSV文件，其中包含选定报表包的所有变量的当前所有标签定义。我们建议您的法律团队审核您的标签设置选项，并且此选项可帮助进行此审核。 无需登录到“数据管理”界面，您即可通过共享 .CSV 文件来进行审核。

1. 单击 **[!UICONTROL 导出CSV]** 此对话框显示在右上方：

   ![](assets/export_csv.png)

1. 选择一个或多个要导出其所有数据管理设置的报表包。

## 编辑隐私标签

请参阅 [分配或编辑报表包隐私标签](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
