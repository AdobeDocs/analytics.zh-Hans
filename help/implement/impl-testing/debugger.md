---
description: 安装旧版Adobe Experience Cloud调试器。 此调试器检查Analytics、Target、Advertising Cloud、Identity Service、DTM和Launch的标记。
title: 旧版Adobe Experience cloud调试器
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 旧版Adobe Experience cloud调试器

> [!IMPORTANT] 不再维护此调试工具。 Adobe建议改用 [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)。

旧版  调试器检查大多数Adobe Experience cloud服务的标记。 使用调试器，您可以查看在站点上的任何给定页面上向Adobe发送的数据。 您可以使用此信息对贵组织的实施进行疑难解答或验证。

## 安装传统调试器

创建JavaScript书签以安装调试器。

### 第1步：复制书签代码

将以下代码复制到剪贴板：

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 第2步：将书签代码粘贴到书签中

每个浏览器处理书签的方式不同，但概念相同。 将创建具有所需名称的书签，并将书签代码作为URL。

#### Chrome

如果您坚持不使用Chrome扩 [展](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)，则可以改用旧版调试器书签工具。

1. 单击右上方的三个圆点，然后转到“书签”&gt;“书签管理器”。 您还可以按 `Ctrl` + `Shift` + `O` (Windows)或 `Cmd` + `Shift` + `O` (Mac)。
2. 在书签管理器的右上角，单击三个圆点，然后单击“添加新书签”。
3. 在“名称”字段中，将其标为“Adobe Experience Cloud调试器”，然后将代码片断粘贴到URL字段中。
4. 使用书签管理器将新书签放在所需位置。

#### Firefox

1. 单击右上方的三行，然后转到“库”&gt;“书签”&gt;“显示所有书签”。 您还可以按 `Ctrl` + `Shift` + `B` (Windows)或 `Cmd` + `Shift` + `B` (Mac)。
2. 单击“组织”&gt;“新建书签”。
3. 在“名称”字段中，将其标为“Adobe Experience Cloud调试器”，然后将代码片断粘贴到“位置”字段中。 标记和关键字字段不是必填字段。
4. 使用库窗口将新书签放在所需位置。

#### Edge

Edge无法手动创建书签，但可以编辑书签URL。

1. 单击URL字段右侧的星形图标，将当前页面加入书签。
2. 将书签命名为“Adobe Experience Cloud Debugger”，并将其保存到所需位置。
3. 单击带有线条的星形图标以打开“收藏夹”栏。
4. 右键单击新创建的书签，选择“编辑URL”。
5. 将代码片断粘贴到文本字段中，然后点击Enter。

#### Safari

Safari无法手动创建书签，但可以编辑书签URL。

1. 单击右上方的“共享”图标，打开书签模式窗口。
2. 将书签命名为“Adobe Experience Cloud Debugger”，并将其保存到所需位置。
3. 单击“书签”&gt;“编辑书签”，然后找到新创建的书签。
4. 右键单击&gt;编辑地址，然后将代码片断粘贴到文本字段中。

## 使用传统调试器

要使用调试器，请导航到站点上所需的页面，然后单击书签。 出现一个弹出窗口，显示发送到Adobe的数据。

> [!NOTE] 某些广告阻止插件和弹出窗口阻止程序可能会干扰调试器窗口的加载。 检查浏览器中阻止的弹出窗口，并允许它们，以便调试器能够正确工作。

调试器具有多个可用选项，所有选项都可自定义数据的显示方式。 这些选项均不影响数据收集。

* **** 显示的Experience cloud产品：显示或隐藏每个Experience cloud产品的图像请求。
* **** URL解码：URL会解码图像请求以匹配报告中显示的内容。 Adobe建议选中此框。
* **** 自动刷新：每隔几秒自动刷新弹出窗口，以检查页面上是否有更多图像请求。 如果需要在调试器中复制／粘贴内容，请禁用自动刷新，以便保持选择。
* **** 友好格式：在图像请求中的有用标签和原始查询字符串之间切换显示格式。 有关详 [细信息，请参阅数据收集查询参数](../js-implementation/data-collection/query-parameters.md) 。

要保存调试器的默认显示选项，请右键单击右上角的“Adobe Debugger”链接，然后复制链接地址。 编辑当前调试器书签并将更新的代码片断粘贴到URL字段中。
