---
description: Ad Hoc Analysis与Analytics细分环境集成，允许您跨Adobe产品构建、共享、管理和应用访客细分。Ad Hoc Analysis为其区段生成器和细分管理器提供基于Java的用户界面，它与其他Analytics工具使用的基于Web的工具相同、匹配服务器调用并提供基于Java的控制台提供相同的特性和功能。
seo-description: Ad Hoc Analysis与Analytics细分环境集成，允许您跨Adobe产品构建、共享、管理和应用访客细分。Ad Hoc Analysis为其区段生成器和细分管理器提供基于Java的用户界面，它与其他Analytics工具使用的基于Web的工具相同、匹配服务器调用并提供基于Java的控制台提供相同的特性和功能。
seo-title: 构建细分
solution: Analytics
title: 构建细分
topic: Ad Hoc Analysis
uuid: e14fb777-900a-4700-8dc7-56a45c678d29
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 构建细分

Ad Hoc Analysis与Analytics细分环境集成，允许您跨Adobe产品构建、共享、管理和应用访客细分。Ad Hoc Analysis为其区段生成器和细分管理器提供基于Java的用户界面，它与其他Analytics工具使用的基于Web的工具相同、匹配服务器调用并提供基于Java的控制台提供相同的特性和功能。

Ad Hoc Analysis 包含用于构建区段的类似功能，另有新功能升级，例如，用于设置区段管理[工作流程](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_workflow)的[区段管理器](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_manage)。与往常一样，您可以在[区段生成器](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_build)中生成并保存区段，或通过 Ad Hoc Analysis 控制台[生成来自流失报表的区段](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=t_seg_fallout)，然后将新区段或扩展区段保存到受众库，以用于常规访问和应用。 ![](assets/seg__overview_ad_hoc.png)

## Ad Hoc Analysis 中的统一分段 {#section_5FA03A06DE054448AD519CE30C39E294}

有关在统一分段环境中生成和管理区段的信息与说明（包括临时分析功能），请参阅[统一分段](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=index)文档。

* [新增功能](../../analyze/ad-hoc-analysis/c-content-ref.md#section_BD58629D1A9346BF879E229FA6BEC7A2)
* [区段定义更改](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_definition)
* [我的现有区段有什么变化？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_76CF47142D1A4FB6A0718AD9073049FE)
* [我的现有区段文件夹有什么变化？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_FB04DCF775694E69B761DCA53F301C30)
* [我可以在区段管理器中管理所有 Analytics 区段吗？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_AF5EDD72C74A4739BD40C4AF125CE489)
* [什么是“点击”容器？与页面查看容器是否有什么不同？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_65BBE60A836C4001938830DDA15DC256)
* [需要哪些权限才能使用、创建和管理区段？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_648DFA3A882146C485A84ED014EEC707)
* [我应该如何处理具有…](../../analyze/ad-hoc-analysis/c-content-ref.md#section_E2C3A1B4B4274D1B86CAA9C0359D049C)
* [Adobe 建议我应该怎样清除区段？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_3AC2D265F9084557A24C6FB39DC6EE49)
* [为什么无法删除此区段？](../../analyze/ad-hoc-analysis/c-content-ref.md#section_0FEB6711031A4ABCA915CDA745ECF38D)
* [关于现有区段所发生改变的更多信息](../../analyze/ad-hoc-analysis/c-content-ref.md#section_83ACAB256F394DCD8B424D8920BDD853)

## 功能 {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* [区段对于所有报表包都是通用的。](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_overview)以前，区段是报表包特有的。
* 您可以通过[区段管理器](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_manage)中的区段共享、标记、验证和批准功能，来设置[工作流程](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_workflow)。

* 经过更新的[区段生成器](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_build_ui)可以简化区段的创建过程。
* 您可以[标记区段](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_tag)，以便稍后进行组织和搜索，而无需使用文件夹。Previously, you used folders (in [!DNL ad hoc analysis]) to organize your segments.

* 您可以在 Ad Hoc Analysis 之外创建[连续区段](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_sequential)。
* 

>[!NOTE]
>
>在临时分析中，您无法向区段添加日期范围。此功能在 Analysis Workspace 中可用。同时，在 Ad Hoc Analysis 中，您也无法使用“仅在序列前/仅在序列后”。

## 我的现有区段有什么变化？ {#section_76CF47142D1A4FB6A0718AD9073049FE}

您的现有区段将与在推出 Analytics 分段之前一样继续工作。已应用了这些区段的任何报表将仍可以正常使用。

以前大多数的预定义包区段将作为[区段模板](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_templates)迁移到区段生成器中。使用区段模板可以快速生成适合一般受众的自定义区段。区段模板无法直接应用于报表，但可以轻松保存到自定义区段。

## 我的现有区段文件夹有什么变化？ {#section_FB04DCF775694E69B761DCA53F301C30}

区段管理器不再使用 (Ad Hoc Analysis) 文件夹，而是使用[标记](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_tag)。您的文件夹名称会自动转换为标记，而且这些标记会应用于各自的区段。

## 我可以在区段管理器中管理所有 Analytics 区段吗？ {#section_AF5EDD72C74A4739BD40C4AF125CE489}

在 Ad Hoc Analysis 区段管理器中，您只能看到属于您的区段（您创建的区段）以及专门与您共享的区段。

## 什么是“点击”容器？与页面查看容器是否有什么不同？ {#section_65BBE60A836C4001938830DDA15DC256}

页面查看容器已重命名为“点击”容器，以表示该容器可分段所有类型的数据，而不仅仅是页面查看。例如，“点击”容器完全包含或排除链接跟踪调用和移动 SDK 中的 [!DNL trackAction] 调用。

请注意，此容器的运行方式并没有发生任何更改，只是进行了重命名。

## 需要哪些权限才能使用、创建和管理区段？ {#section_648DFA3A882146C485A84ED014EEC707}

所有用户均可以创建和编辑个人区段。这些区段可以直接与任何其他 Analytics 用户共享。

管理员可以编辑任何区段，与群组[共享区段](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=t_seg_share)，并为组织[设置权限](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_rights)以访问区段。

## 我应该怎样处理具有相同名称，但可能有不同定义的重复区段？ {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

由于区段在多个报表包中使用，您可能会发现有多个区段具有相同的名称。我们建议您

* 重命名名称相同但定义不同的区段，或者
* 删除不再需要的区段。

## Adobe 建议我应该怎样清除区段？ {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* 使用原有标记对所有区段添加标记。
* 审查您拥有的区段。
* 将区段添加到区段库（如果适用）。
* 批准符合规范的区段。
* 根据最佳实践标记区段。

## 为什么无法删除此区段？ {#section_0FEB6711031A4ABCA915CDA745ECF38D}

如果区段已[发布到 Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=t_publish_audience_segment)，则无法删除或编辑该区段。但是，您可以复制该区段，然后编辑其复制版本。

## 关于现有区段所发生改变的更多信息 {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 区段类别 </th> 
   <th colname="col2" class="entry"> 这些区段有什么变化？ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 收藏区段（Ad Hoc Analysis） </td> 
   <td colname="col2">在 Adobe Analytics 中，这些 Ad Hoc Analysis 区段显示为常规区段。 <p>请不要将这些区段与区段管理器中可用于将区段标记为收藏的“收藏夹”功能混淆。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">预配置区段： 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">单页面访问量 </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">来自移动设备的访问量 </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">来自免费搜索的访问量 </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">来自付费搜索的访问量 </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">使用访客 ID Cookie 的访问量 </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些区段将作为<a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_templates" format="http" scope="external">区段模板</a>迁移到区段生成器中。 </p> <p>已应用这些区段的现有报表将仍可正常使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Experience Cloud（包）区段： 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">非顾客 </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">顾客 </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">首次访问量 </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">社交网站访问量 </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">访问时间超过 10 分钟的访问量* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">之前访问次数超过 5 次的访问量* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Facebook 访问量* </li> 
    </ul> </td> 
   <td colname="col2"> <p> 其中大多数区段（使用星号 * 标记的区段除外）将作为<a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_templates" format="http" scope="external">区段模板</a>迁移到区段生成器中。此外，还添加了多个新区段模板。 </p> <p>已应用这些区段的现有报表将仍可正常使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">管理员区段 <p>（也称为“全局”区段） </p> </td> 
   <td colname="col2"> <p> <b>管理员</b>区段将迁移到新的区段界面中，并将显示为与每个人共享的区段。 </p> <p>这些区段的所有者被设置为使用登录公司管理员用户列表中最旧帐户的管理员，但所有管理员都可以删除、编辑和共享这些区段。 </p> <p>管理控制台中管理员创建和管理这些全局区段的区段管理界面不再可用。管理员应使用新的区段生成器创建区段，并将其与相应组、个人或每个人共享。 </p> </td> 
  </tr> 
 </tbody> 
</table>

