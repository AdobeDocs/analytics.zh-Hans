---
description: 成功实施链接跟踪的关键是理解 s.linkTrackVars 和 s.linkTrackEvents 变量。这样，您可以在用户操作中传递自定义变量值。
keywords: Analytics 实施
seo-description: 成功实施链接跟踪的关键是理解 s.linkTrackVars 和 s.linkTrackEvents 变量。这样，您可以在用户操作中传递自定义变量值。
seo-title: 使用 s.linkTrackVars 和 s.linkTrackEvents
solution: Analytics
title: 使用 s.linkTrackVars 和 s.linkTrackEvents
topic: 开发人员和实施
uuid: f6b7019b-987b-4b7d-a446-80205f7 cc36 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用 s.linkTrackVars 和 s.linkTrackEvents

成功实施链接跟踪的关键是理解 s.linkTrackVars 和 s.linkTrackEvents 变量。这样，您可以在用户操作中传递自定义变量值。

如果您要实施自定义链接跟踪，并设置[!UICONTROL 自定义]变量和&#x200B;*`events`*&#x200B;请确保 [!UICONTROL 您的s. linkTrackVars] 变量包含您要传递的所有变量的逗号分隔列表，包括变量 *`events`* 。确保 [!UICONTROL s.linkTrackEvents] 包含要传递的所有事件列表（以逗号分隔）。

设置 [!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 不会实际设置这些变量/事件，只是准备要执行此操作的 [!DNL Analytics] 代码。您仍需要手动设置变量，如下面的示例所示：

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

请注意 [!UICONTROL s.linkTrackVars] 变量中列出的事件。传递的个别事件可能包含在 [!UICONTROL s.linkTrackEvents] 变量中，同时还会包含在函数后面的 [!UICONTROL s.events] 中。在函数后期填充变量之前，传递的每个变量都会列在 [!UICONTROL s.linkTrackVars] 中。另外，“event9”已包含在 [!UICONTROL s.linkTrackEvents] 中，但未包含在 [!UICONTROL s.event ] 中。不会记录该事件，但如果用户选择设置 s.events="event5,event9"，则可以记录该事件。

自动文件下载和[!UICONTROL 退出]链接跟踪的工作方式并不相同。[!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 包含在标准 [!DNL s_code.js] 文件中，并且都被设置为 none。这些变量在 [!DNL s_code.js] 文件中通常设置为 none，以便自动链接跟踪（不同于[!UICONTROL 自定义链接跟踪]）可以使用全局 JavaScript 文件中设置的 [!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 值。每次记录文件下载或[!UICONTROL 退出]链接时，无论这些变量的现有值是什么，它们也都会照常传递。

请考虑以下示例：页面加载时 s.channel="Home"，并且在 [!DNL s_code.js] 文件中 s.linkTrackVars="channel"。如果用户点击下载文件，自动文件下载跟踪将数据传递到 [!DNL Analytics] 中，其中包括页面加载时设置的 [!UICONTROL s.channel] 值。“Home”被传递两次，导致[!UICONTROL 网站区域]报表中的页面查看数据因此值而虚增。

Adobe 强烈建议将全局 JavaScript 文件中的 [!UICONTROL s.linkTrackVars] 和 [!UICONTROL s.linkTrackEvents] 设置保留为“none”，并在必要时，通过[!UICONTROL 自定义链接跟踪]实施明确设置它们。
