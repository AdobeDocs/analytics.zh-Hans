---
title: 旧版 Adobe Experience Cloud Debugger
description: 安装旧版 Adobe Experience Cloud Debugger。此调试器可检查 Analytics、Target、Advertising Cloud、Identity Service 和 Data Collection 的标记。
feature: Validation
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 100%

---

# 旧版 Adobe Experience Cloud Debugger

>[!IMPORTANT]
>
> Adobe 将不再维护此调试工具。Adobe 建议改用 [Adobe Experience Cloud Debugger Chrome 扩展](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans)。

[!UICONTROL 旧版 Debugger] 可检查大多数 Adobe Experience Cloud 服务的标签。通过使用该调试器，您可以查看在网站上的任何给定页面向 Adobe 发送了哪些数据。您可以使用此信息对贵组织的实施进行故障诊断或验证。

## 安装旧版 Debugger

创建 JavaScript 小书签以安装该调试器。

### 第 1 步：复制小书签代码

将以下代码复制到剪贴板：

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 第 2 步：将小书签代码粘贴到书签中

虽然每个浏览器处理书签的方式不同，但基本概念却相同。创建书签时，将使用所需的名称并使用小书签代码作为 URL。

#### Chrome

如果您坚持不使用 [Chrome 扩展](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans)，则可以改用旧版 Debugger 小书签。

1. 单击右上方的三个圆点，然后转到“书签”>“书签管理器”。此外，您还可以按 `Ctrl` + `Shift` + `O` (Windows) 或 `Cmd` + `Shift` + `O` (Mac)。
2. 在书签管理器的右上方，单击三个圆点，然后单击“添加新书签”。
3. 在“名称”字段中，将其标记为“Adobe Experience Cloud Debugger”，然后将相应的代码段粘贴到“URL”字段中。
4. 使用书签管理器将新建的小书签放在所需位置。

#### Firefox

1. 单击右上方的三条横线，然后转到“库”>“书签”>“显示所有书签”。此外，您还可以按 `Ctrl` + `Shift` + `B` (Windows) 或 `Cmd` + `Shift` + `B` (Mac)。
2. 单击“组织”>“新建书签”。
3. 在“名称”字段中，将其标记为“Adobe Experience Cloud Debugger”，然后将相应的代码段粘贴到“位置”字段中。“标签”和“关键字”字段不是必填字段。
4. 使用库窗口将新建的小书签放在所需位置。

#### Edge

Edge 无法手动创建小书签，但可以将书签 URL 编辑为小书签。

1. 单击“URL”字段右侧的星形图标，以将当前页面加入书签。
2. 将书签命名为“Adobe Experience Cloud Debugger”，并将其保存到所需位置。
3. 单击带有线条的星形图标以打开“收藏夹”栏。
4. 右键单击新创建的书签，选择“编辑 URL”。
5. 将相应的代码段粘贴到文本字段中，然后按 Enter。

#### Safari

Safari 无法手动创建小书签，但可以将书签 URL 编辑为小书签。

1. 单击右上方的“共享”图标，以打开书签模式窗口。
2. 将书签命名为“Adobe Experience Cloud Debugger”，并将其保存到所需位置。
3. 单击“书签”>“编辑书签”，然后找到新创建的书签。
4. 右键单击并选择“编辑地址”，然后将相应的代码段粘贴到文本字段中。

## 使用旧版 Debugger

导航到网站上的所需页面，然后单击小书签。此时将出现一个弹出窗口，其中显示了发送到 Adobe 的数据。

>[!NOTE]
>
> 某些广告拦截插件和弹出窗口阻止程序可能会妨碍调试器窗口的加载。请检查浏览器中遭到阻止的弹出窗口，并允许显示这些弹出窗口，以便调试器能够正常工作。

调试器具有多个可用选项，所有这些选项都可以自定义数据的显示方式。这些选项均不影响数据收集。

* **显示的 Experience Cloud 产品：**&#x200B;显示或隐藏每个 Experience Cloud 产品的图像请求。
* **URL 解码：** URL 将解码图像请求以匹配报表中显示的内容。Adobe 建议保留选中此框。
* **自动刷新：**&#x200B;每隔几秒钟自动刷新一次弹出窗口，以检查页面上是否有更多图像请求。如果需要在调试器中复制/粘贴内容，请禁用自动刷新，以便保留所做的选择。
* **友好格式：**&#x200B;在图像请求中的有用标签和原始查询字符串之间切换显示格式。有关详细信息，请参阅[数据收集查询参数](query-parameters.md)。

要保存调试器的默认显示选项，请右键单击右上角的“Adobe Debugger”链接，然后复制该链接地址。编辑当前调试器小书签并将更新的代码段粘贴到“URL”字段中。
