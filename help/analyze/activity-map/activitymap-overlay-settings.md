---
description: 您可以通过“Activity Map 设置”面板，为所有类型的叠加图可视化修改设置和属性。
title: 配置 Activity Map 设置
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
translation-type: tm+mt
source-git-commit: 700d3b21a238af23719b291fe60df207e916bb87
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 50%

---

# 配置 Activity Map 设置

您可以通过“Activity Map 设置”面板，为所有类型的叠加图可视化修改设置和属性。

通过单击 Activity Map 工具栏中的齿轮图标，可以访问“Activity Map 设置”面板。

## 常规设置 {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 公司]** | 选择适用的登录公司。 |
| **[!UICONTROL 报表包]** | 您可以访问的报表包列表不再局限于网页标签中定义的报表包。现在，您可以将选定的报表包（对应于页面上的标签之一）替换为其他报表包。不需要将此新报表包链接到页面上的标签。如果您在“Activity Map设置”中更改选定的报表包，则“保存”过程会刷新所有受影响的Analytics报表。<br>**重要说明**: [!UICONTROL 虚拟报] 表包与实时模式 [!UICONTROL 不兼容]，只与标 [!UICONTROL 准模式兼容]。如果您处于标准报表包的[!UICONTROL 实时模式]，但在此对话框中选择[!UICONTROL 虚拟报表包]，则单击此处的&#x200B;**[!UICONTROL 确定]**&#x200B;后，将显示标准模式。 此外，将重新初始化日历控件以匹配报表包的日历类型（公历、零售、自定义……）。 |
| **[!UICONTROL 页面名称]** | 应用这些设置的页面。 |
| **[!UICONTROL 语言]** | 语言选项对应于为 Adobe Analytics 提供的语言。 |
| **[!UICONTROL 为叠加图添加以下标签]** | <ul><li>**[!UICONTROL 没有标签]**：仅适用于渐变叠加图。在这种情况下，叠加的颜色传达了链接排名的感觉</li><li>**[!UICONTROL 数值]**：该链接的原始总量度</li><li>**[!UICONTROL 百分比]**：该链接的量度与页面总量度的百分比。</li><li>**[!UICONTROL 排名]**：该链接在呈现的页面所展示的全部链接中的排名</li></ul> |
| **[!UICONTROL 标签字体大小]** | 允许您使用滑块来增加/缩减叠加图标签的字体大小，以改善可读性。 |
| **[!UICONTROL 渐变/气泡颜色]** | 要显示渐变或气泡叠加可视化的叠加链接排名，请在一系列颜色中进行选择。 |
| **[!UICONTROL 颜色渐变依据]** | <ul><li>**[!UICONTROL 前 30 位排名]**：颜色浓度可以被标准化为前 30 位的值。</li><li>**[!UICONTROL 绝对量度值]**：颜色浓度可以行使绝对量度值的作用。</li></ul> |
| **[!UICONTROL 渐变透明度]** | 为渐变叠加图选择透明度。此设置不影响[!UICONTROL Bubble]叠加。 |

## 标准设置{#section_24DB95376E1A448494ECF3F57743FC19}

这些设置适用于标准模式叠加。

![](assets/settings_standard.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 动态数据过滤]** | 此下拉列表允许您显示<ul><li>（默认）页面上的所有链接</li><li>页面上排名链接的顶部（最高）或底部（最低）#，其中#可以是1、10、50或100的选项。</li></ul> |
| **[!UICONTROL 隐藏未收到点击的链接的叠加]**。 | 一个复选框，用于切换没有数据的链接的叠加的可见性。<ul><li>（默认）如果选中此复选框，则当链接没有ActivityMap链接数据时，不显示叠加。</li><li>如果未选中此复选框，则如果链接没有ActivityMap链接数据，则显示叠加并且其标签为“ — ”，即表示“N/A”（不适用）。 |

## 实时设置{#section_D30F6E62FB5D404090B588F396A460AF}

这些设置适用于实时模式叠加。

![](assets/settings_live.png)

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 显示排名最前的]** | 要将&#x200B;**[!UICONTROL Nuthame]**&#x200B;或&#x200B;**[!UICONTROL Nusters]**（或两者）显示为叠加，请选择链接数。 |
| **[!UICONTROL 排除最低值 (%)]** | 选择此选项可利用稀疏数据排除获胜方-失败方链接。按照所需的百分比，将链接变更的最低值排除，以便专门查看拥有足够数据来显示相关得与失的链接。百分比是根据页面上的链接数量计算的。例如，过滤掉200个链接列表的底部10%将过滤掉底部20个链接。 |
| **[!UICONTROL 自动更新数据]** | 允许您决定在计算新时段时，界面中显示的Analytics数据是否自动更新。 |
| **[!UICONTROL 自动更新时段]** | 选中此选项后，每次进行新的数据检索时就会刷新网页，这样页面中的链接就可以更加及时地与收集的数据保持同步。 |
