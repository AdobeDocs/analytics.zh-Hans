---
title: Activity Map 常见问题解答
description: 与Activity Map相关的常见问题解答。
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 15%

---

# Activity Map 常见问题解答

与Activity Map相关的常见问题解答。

+++如何向Activity Map授予权限？

在[Adobe Admin Console](/help/admin/admin-console/home.md)中处理使用Activity Map及其相关维度的权限。

Activity Map所需的[权限项](/help/admin/admin-console/permissions/product-profile.md)包括：

* **[!UICONTROL Analytics工具]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL 分析工具]** > **[!UICONTROL 区段发布]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map滚动范围]**
* **[!UICONTROL Dimension]** > **[!UICONTROL 按地区Activity Map的链接]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map地区]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map链接]**
* **[!UICONTROL Dimension]** > **[!UICONTROL Activity Map页面]**

有关详细信息，请参阅[Analytics工具的产品配置文件权限](/help/admin/admin-console/permissions/analytics-tools.md)。

+++

+++所有Analytics客户都可以访问Activity Map吗？

具有Adobe Analytics Standard、Premium和Ultimate合同的组织有权访问Activity Map。 这些合同类型代表大多数Adobe Analytics客户。

+++

+++Activity Map如何支持单页应用程序(SPA)？

每隔几秒，Activity Map会扫描网页以查找更改。 Activity Map查找页面上的新内容而无需重新加载，但此新内容始终归因于第一个页面维度值。

* Activity Map 检查以确定它知道的链接的可见性是否发生了更改。如果发现了可见性的更改，则“页面上的链接”表上该链接的“现在”列将使用[!UICONTROL 已显示]或[!UICONTROL 已隐藏]更新。

* 当用户交互创建新内容时，AppMeasurement确定为链接的任何新元素将添加到[!UICONTROL Links On Page]表中。 Activity Map 发送包括这些新链接的新数据请求。当返回数据请求时，新链接将显示在[!UICONTROL Links On Page]表中。

+++

+++Activity Map是否提供有关已查看但未单击的链接的数据？

否，Adobe不会自动跟踪仅被查看的链接。

+++

+++Activity Map支持哪些浏览器和版本？

Activity Map 支持大多数现代浏览器的最新版本。

+++

+++Activity Map是否会增加服务器调用次数？

Activity Map 本身不会发送服务器调用。相反，Activity Map上下文数据变量包含在后续页面上的Analytics页面查看调用中。 但是，Web SDK上某些以前版本的Activity Map会发送单独的Activity Map数据调用。 如果您使用的是最新版本的Web SDK，则Activity Map数据将与以下事件合并。

+++

+++为什么叠加中会缺少一些排名数字？

某些链接（如菜单中包含的链接）在页面中处于隐藏状态。 因此，它们对应的链接叠加也不显示。 排名的计算针对页面上的所有链接，包括隐藏链接。

+++

+++“所有链接”报表中如何确定链接排名？

* **在“渐变”和“气泡”模式中**：指标列决定排名。 对于具有相同量度值的链接，其排名由链接ID的字母顺序进一步确定。
* **在获胜方和失败方模式中**：获得的百分比列决定排名。 对于具有相同增益的链接而言，其排名由链接 ID 的字母顺序进一步确定。

+++

+++Activity Map如何处理使用多个报表包的页面？

默认情况下，Activity Map使用与页面中第一个标记关联的报表包。 您可以通过&#x200B;**[!UICONTROL Activity Map设置]** > **[!UICONTROL 其他]**&#x200B;选项卡选择其他报表包。

+++

+++Activity Map多长时间在页面上扫描Adobe Analytics？

Activity map 在页面完成事件后最多 20 秒扫描是否存在 Adobe Analytics。

+++

+++Activity Map如何处理动态内容？

Activity Map 每两秒检查一次是否发现网页的状态有更改，例如：

* HTML 内容变为可见
* 隐藏了 HTML 内容
* 插入了新的 HTML 内容

如果隐藏或显示了内容，则扩展会自动将受影响的链接状态（以及因此形成的叠加图）从“隐藏”更改为“显示”，或者从“显示”更改为“隐藏”。 如果注入了新内容，则应用程序会检索关联的链接、从中提取分析数据并为这些链接添加叠加图。

+++

+++页面流量报表基于什么量度？

显示的所有数据基于页面查看量。

+++

+++能否通过数据馈送导出Activity Map数据？

是的。Activity Map使用的[数据馈送列](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)包括：

* Activity Map链接： `clickmaplink`
* Activity Map页面： `clickmappage`
* Activity Map地区： `clickmapregion`
* 按地区Activity Map链接： `clickmaplinkbyregion`

+++

+++区段在实时模式下是否可以使用？

否，区段不适用于实时模式。

+++

+++Activity Map是否与虚拟报表包兼容？

是的。但是，由于虚拟报表包的限制，Activity Map的实时模式与虚拟报表包不兼容。

+++

+++如何禁用Activity Map？

禁用Activity Map的方法取决于您的实现类型：

* **Web SDK扩展**：在扩展配置设置中，取消选中&#x200B;**[!UICONTROL 收集内部链接点击次数]**、**[!UICONTROL 收集外部链接点击次数]**&#x200B;和&#x200B;**[!UICONTROL 收集下载链接点击次数]**&#x200B;复选框。
* **Web SDK JavaScript库**：将[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)设置为`false`。
* **Analytics扩展**：在扩展配置设置中，取消选中标记为&#x200B;**[!UICONTROL 使用Activity Map]**&#x200B;的框。
* **AppMeasurement**：在`AppMeasurement.js`中移除或注释掉Activity Map模块，或使用空正文覆盖模块函数调用：

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++使用Activity Map覆盖的系统要求是什么？

您可以将最新版本的Chrome、Edge或Firefox与Activity Map扩展结合使用。

+++

+++将Activity Map用于个人身份信息时，必须考虑什么？

考虑以下可使用Activity Map收集个人身份数据的情况：

* **电子邮件链接**：如果可以通过单击电子邮件地址来打开用户的邮件客户端，则Activity Map可以收集所单击的电子邮件地址。
* **用户ID链接**：访客登录后，Activity Map可以记录包含该访客用户ID的任何链接。
* **敏感信息链接**：对于金融机构，如果帐号等敏感信息是链接且访客点击了这些链接，则可以跟踪这些信息。
* **包含个人信息的链接**：对于医疗保健网站，链接可以包含个人信息。 如果访客单击这些链接，则Activity Map会收集该链接文本。

+++

+++默认情况下，Activity Map跟踪哪些数据？

Activity Map跟踪以下元素：

* 具有`href`属性的`<a>`或`<area>`标记。 默认情况下，不会跟踪锚点标记链接(`#`)。
* 设置`s_objectID`变量的`onclick`特性
* 带有值或子文本的`<input>`标记或`submit`按钮
* 类型为`image`且属性为`src`的`<input>`标记
* 不带属性`type="button"`的`<button>`标记。 如果要跟踪`<button>`标记，请考虑改用`role="button"`或`submit="button"`等属性。

+++

+++Activity Map自动跟踪的链接有哪些示例？

以下是Activity Map具有跟踪链接所需的所有信息的一些示例。

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Activity Map不会自动跟踪的链接有哪些示例？

* 锚标记没有有效的`href`
* [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md)或[`tl()`](/help/implement/vars/functions/tl-method.md)方法都不存在
* 表单输入元素中缺少`src`属性

以下是Activity Map不跟踪点击的一些示例：

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
