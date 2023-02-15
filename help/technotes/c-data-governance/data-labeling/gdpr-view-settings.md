---
description: “数据治理的隐私标签”对话框概述了报告包的隐私标签和命名空间。您还可以从此处将设置导出到 .csv 文件。
title: 查看/管理数据治理的隐私标签
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 1ca7040156f7f2105a9625f921de3d90b4175056
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 查看/管理数据治理的隐私标签

**[!UICONTROL 数据治理的隐私标签]**&#x200B;对话框概述了报告包的隐私标签和命名空间。您还可以从此处将设置导出到 .csv 文件。

## 查看隐私标签 {#view-privacy}

1. 登录到 Adobe Experience Cloud。
2. 导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据配置和收集]** > **[!UICONTROL 数据治理]**。

   >[!NOTE]
   >
   >如果您没有看到此菜单项，则需要将您添加到 [Admin Console 中的产品配置文件](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)，并为您提供对此功能的各种权限。

3. 在右上角，选择要查看或管理其隐私标签的报告包。

![](assets/privacy_labeling.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 组件名称]** | 此列列出了属于此报告包的所有组件（维度、量度）。 |
| **[!UICONTROL 身份]** | 身份数据“I”标签用于对可识别或联系特定人员的数据进行分类。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#data-privacy-identity-labels) |
| **[!UICONTROL 敏感度]** | 敏感数据“S”标签用于对诸如地理数据之类的敏感数据进行分类。未来，会引入其他敏感数据标签，用于识别其他类型的敏感信息。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#sensitive-data-labels) |
| **[!UICONTROL GDPR 访问]** | 通过数据治理标签，用户可将反映与隐私相关的考虑因素和合同条件的数据分类，以符合法规和公司政策。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#data-privacy-access-labels) |
| **[!UICONTROL GDPR 删除]** | 仅当包含允许将点击与数据主体关联的值（即允许标识数据主体）的字段时，才需要删除标签。 [了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#data-privacy-delete-labels) |
| **[!UICONTROL 命名空间]** | 在为变量设置 ID-DEVICE 或 ID-PERSON 标签时，系统会提示您提供一个命名空间。您可以使用先前已定义的命名空间或者定义一个新的命名空间。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-labels.html?lang=en#provide-namespace) |
| **[!UICONTROL 类别]** | 指组件类型，如标准组件、转化变量等。 |

{style=&quot;table-layout:auto&quot;}

## 将隐私标签复制到报告包  {#copy-to-rs}

如果要将相同的“数据隐私”设置应用于多个报告包，请执行以下步骤：

1. 选择要复制的变量。请注意，您一次只能复制一个变量的标签。
1. 单击“数据治理”对话框底部的&#x200B;**[!UICONTROL 复制到报告包]**。

   ![复制到报告包](assets/copy_to_reportsuite.png)

1. 生成的屏幕将显示变量名称、您尝试复制的当前应用的标签、报告包及其 ID，以及目标报告包中的设置是否匹配。

   ![将标签复制到报告包](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >请记住，您选择的所有报表包都必须映射到您的Experience Cloud组织。

   将一个变量或一组变量的标签复制到不同的报告包时，复制的标签会转到目标报告包中相应位置的变量中。对于标准组件、列表变量和成功事件，标签将被复制到目标报告包中具有&#x200B;**相同名称**&#x200B;的变量中。

   但是，对于转化变量(eVar)和流量Dimension(prop)，复制的内容会转到变量，并且 **相同数字** 中。 例如，eVar12 将被复制到所有目标报告包的 eVar12 中。在确定复制的目标时，会忽略这些变量的名称。如果相应的变量未在目标报告包中启用，则针对该变量的标签复制将会失败。

   在复制为变量定义的分类标签时，标签将被复制到与目标报告包中相应变量对应的（例如 eVar7 至 eVar7）分类中，该分类的名称要与被复制的分类名称相同。否则，该分类标签的复制将会失败。

1. 选中设置匹配的一个或多个报告包旁边的框。
1. 单击&#x200B;**[!UICONTROL 应用]**。

   在应用标签后，将显示状态消息。 状态消息将包含复制失败的所有目标变量或分类及其报告包的名称。

   >[!IMPORTANT]
   >
   >您应该始终检查目标报表包，以确保标签已正确复制。 对于具有 ID 或 DEL 标签的变量来说，这一点尤为重要。

## 导出到 .csv 文件 {#export-csv}

您可以下载一个CSV文件，其中包含选定报表包的所有变量的当前所有标签定义。 我们建议您的法律团队审核您的标签设置选项，并且此选项可帮助进行此审核。 无需登录到“数据治理 UI”，即可通过共享 .CSV 文件来进行审查。

1. 单击右上角的&#x200B;**[!UICONTROL 导出 CSV]**，此对话框将显示：

   ![](assets/export_csv.png)

1. 选择要为其导出所有数据治理设置的一个或多个报告包。

## 编辑隐私标签 {#edit}

参考[分配或编辑报告包隐私标签](/help/technotes/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)。
