---
title: 旧版调试器
description: 安装旧版调试器。 此调试器可检查Analytics、Target、Advertising、Identity Service的标记以及数据收集标记。
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/igbKBwN0NmXCPRi9Rc1UtG7Ty1ffpd0rwyWEOTWPWdk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 75%

---

# 旧版调试器

>[!IMPORTANT]
>
>Adobe 将不再维护此调试工具。 Adobe建议改用[Adobe CX Enterprise Debugger Chrome扩展](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)。

[!UICONTROL 旧版Debugger]可检查大多数Adobe CX Enterprise服务的标签。 通过使用该调试器，您可以查看在网站上的任何给定页面向 Adobe 发送了哪些数据。 您可以使用此信息对贵组织的实施进行故障诊断或验证。

## 安装旧版 Debugger

创建 JavaScript 小书签以安装该调试器。

### 第 1 步：复制小书签代码

将以下代码复制到剪贴板：

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 第 2 步：将小书签代码粘贴到书签中

虽然每个浏览器处理书签的方式不同，但基本概念却相同。 创建书签时，将使用所需的名称并使用小书签代码作为 URL。

#### Chrome

如果您坚持不使用 [Chrome 扩展](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans)，则可以改用旧版 Debugger 小书签。

1. 单击右上方的三个圆点，然后转到“书签”>“书签管理器”。 此外，您还可以按 `Ctrl` + `Shift` + `O` (Windows) 或 `Cmd` + `Shift` + `O` (Mac)。
2. 在书签管理器的右上方，单击三个圆点，然后单击“添加新书签”。
3. 在“名称”字段中，将其标记为“旧版调试器”，然后将相应的代码段粘贴到“URL”字段中。
4. 使用书签管理器将新建的小书签放在所需位置。

#### Firefox

1. 单击右上方的三条横线，然后转到“库”>“书签”>“显示所有书签”。 此外，您还可以按 `Ctrl` + `Shift` + `B` (Windows) 或 `Cmd` + `Shift` + `B` (Mac)。
2. 单击“组织”>“新建书签”。
3. 在“名称”字段中，将其标记为“旧版调试器”，然后将相应的代码段粘贴到“位置”字段中。 “标签”和“关键字”字段不是必填字段。
4. 使用库窗口将新建的小书签放在所需位置。

#### Edge

Edge 无法手动创建小书签，但可以将书签 URL 编辑为小书签。

1. 单击“URL”字段右侧的星形图标，以将当前页面加入书签。
2. 将书签命名为“旧版调试器”，并将其保存到所需位置。
3. 单击带有线条的星形图标以打开“收藏夹”栏。
4. 右键单击新创建的书签，选择“编辑 URL”。
5. 将相应的代码段粘贴到文本字段中，然后按 Enter。

#### Safari

Safari 无法手动创建小书签，但可以将书签 URL 编辑为小书签。

1. 单击右上方的“共享”图标，以打开书签模式窗口。
2. 将书签命名为“旧版调试器”，并将其保存到所需位置。
3. 单击“书签”>“编辑书签”，然后找到新创建的书签。
4. 右键单击并选择“编辑地址”，然后将相应的代码段粘贴到文本字段中。

## 使用旧版 Debugger

导航到网站上的所需页面，然后单击小书签。 此时将出现一个弹出窗口，其中显示了发送到 Adobe 的数据。

>[!NOTE]
>
>某些广告拦截插件和弹出窗口阻止程序可能会妨碍调试器窗口的加载。 请检查浏览器中遭到阻止的弹出窗口，并允许显示这些弹出窗口，以便调试器能够正常工作。

调试器具有多个可用选项，所有这些选项都可以自定义数据的显示方式。 这些选项均不影响数据收集。

* **[!UICONTROL 显示的Experience Cloud产品]**：显示或隐藏每个CX Enterprise产品的图像请求。
* **[!UICONTROL URL解码]**： URL将解码图像请求以匹配报表中显示的内容。 Adobe 建议保留选中此框。
* **[!UICONTROL 自动刷新]**：每隔几秒自动刷新一次弹出窗口，以检查页面上是否有更多图像请求。 如果需要在调试器中复制/粘贴内容，请禁用自动刷新，以便保留所做的选择。
* **[!UICONTROL 友好格式]**：在图像请求中的有用标签和原始查询字符串之间切换显示格式。 有关详细信息，请参阅[数据收集查询参数](query-parameters.md)。

要保存调试器的默认显示选项，请右键单击右上角的“Adobe Debugger”链接，然后复制该链接地址。 编辑当前调试器小书签并将更新的代码段粘贴到“URL”字段中。
