---
description: 如果您习惯于在 Ad Hoc Analysis 中使用区段生成器，那么此常见问题解答解释了现有区段和文件夹的情况以及需要采取哪些操作。
keywords: 细分；segments
seo-description: 如果您习惯于在 Ad Hoc Analysis 中使用区段生成器，那么此常见问题解答解释了现有区段和文件夹的情况以及需要采取哪些操作。
seo-title: 适用于 Ad Hoc Analysis 的过渡指南
solution: Analytics
title: 适用于 Ad Hoc Analysis 的过渡指南
topic: 区段
uuid: d409d71a-f8 d9-42a2-add2-37d426 cd40 d1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 适用于 Ad Hoc Analysis 的过渡指南

如果您习惯于在 Ad Hoc Analysis 中使用区段生成器，那么此常见问题解答解释了现有区段和文件夹的情况以及需要采取哪些操作。

## 功能 {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* 区段对于所有报表包都是通用的。以前，区段是报表包特有的。
* Ad Hoc Analysis 包含对区段生成器的更新，以及对区段管理器的完整更新。
* 您现在可以标记区段，以便稍后进行组织和搜索，而无需使用文件夹。Previously, you used folders in [!DNL Ad Hoc Analysis] to organize your segments.

## 我的现有区段有什么变化？{#section_76CF47142D1A4FB6A0718AD9073049FE}

您的现有区段将继续和以前一样使用。已应用了这些区段的任何报表将仍可以正常使用。

以前大多数的预定义包区段将作为区段模板迁移到区段生成器中。使用区段模板可以快速生成适合一般受众的自定义区段。区段模板无法直接应用于报表，但可以轻松保存到自定义区段。

在区段生成器中，区段模板使用特殊的图标进行标记。

## 我的现有区段文件夹有什么变化？ {#section_FB04DCF775694E69B761DCA53F301C30}

区段管理器不再使用 Ad Hoc Analysis 文件夹，而是使用标签。您的文件夹名称会自动转换为标记，而且这些标记会应用于各自的区段。

## 已应用区段的计划报表有什么变化？ {#section_81D1B215533C46E99E17BAE7A3376FDF}

计划报表会继续以您所定义的区段正常运行。

删除区段后，应用该区段的计划报表和功能板可继续正常使用，即区段或功能板继续使用删除的区段。

## 什么是“点击”容器？与页面查看容器是否有什么不同？ {#section_65BBE60A836C4001938830DDA15DC256}

页面查看容器已重命名为“点击”容器，以表示该容器可分段所有类型的数据，而不仅仅是页面查看。例如，点击容器完全包含或排除链接跟踪调用和移动 SDK 中的 trackAction 调用。

请注意，此容器的运行方式并没有发生任何更改，只是进行了重命名。

## 需要哪些权限才能使用、创建和管理区段？ {#section_648DFA3A882146C485A84ED014EEC707}

所有用户均可以创建和编辑个人区段。这些区段可以直接与任何其他 Analytics 用户共享。“Ad Hoc Analysis”用户可以查看每个人创建的区段，以及直接与该用户共享的那些区段。

在“统一的分段”Web 控制台中，管理员可以编辑任意区段，并且与群组以及组织中的每个人共享区段。

## 我可以看到公司的所有区段吗？ {#section_AC2D328C7410419E80C7C17971CD95B3}

会显示您拥有的所有 Ad Hoc Analysis 区段，以及明确与您共享的区段。

## 我可以在区段管理器中管理所有 Analytics 区段吗？ {#section_AF5EDD72C74A4739BD40C4AF125CE489}

Ad Hoc Analysis 仅显示由您生成的区段或明确与您共享的区段。仅对于 Ad Hoc Analysis 而言，您可以使用区段管理器（组织区段）来管理 Ad Hoc Analysis 区段。可以使用“统一的分段”中的区段管理器来管理所有的 Analytics 区段。

## 我应该怎样处理具有相同名称，但可能有不同定义的重复区段？ {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

由于区段在多个报表包中使用，您可能会发现有多个区段具有相同的名称。我们建议您

* 重命名名称相同但定义不同的区段，或者
* 删除不再需要的区段。

## Adobe 建议我应该怎样清除区段？ {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* 使用原有标记对所有区段添加标记。
* 审查您拥有的区段。
* 将区段添加到区段库（如果适用）。
* 批准符合规范的区段。

## 为什么无法删除此区段？ {#section_0FEB6711031A4ABCA915CDA745ECF38D}

如果区段已发布到 Experience Cloud，则无法删除或编辑该区段。但是，您可以复制该区段，然后编辑其复制版本。

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
   <td colname="col1"> Ad Hoc Analysis 中的收藏区段 </td> 
   <td colname="col2">在 Adobe Analytics 中，这些 Ad Hoc Analysis 区段显示为常规区段。 <p>请不要将这些区段与区段管理器中可用于将区段标记为收藏的“收藏夹”功能混淆。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">临时分析中预配置的区段： 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">单页面访问量 </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">来自移动设备的访问量 </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">来自免费搜索的访问量 </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">来自付费搜索的访问量 </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">使用访客 ID Cookie 的访问量 </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些区段将作为区段模板迁移到区段生成器中。 </p> <p>已应用这些区段的现有报表将仍可正常使用。 </p> </td> 
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
   <td colname="col2"> <p> 其中大多数区段（使用星号 * 标记的区段除外）将作为区段模板迁移到区段生成器中。此外，还添加了多个新区段模板。 </p> <p>已应用这些区段的现有报表将仍可正常使用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

