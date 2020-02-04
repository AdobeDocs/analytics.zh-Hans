---
title: addProductEvar
description: 将销售eVar添加到产品变量。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：addProductEvar

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `addProductEvar` 件允许您轻松地将使用产品语法的Adobe Analytics销售eVar添加到产品变量中，而不必担心产品变量的现有内容是否会被更改／移动／删除。 如果您希望将产品语法推销eVar轻松添加到变量，Adobe建议使用此插 `products` 件。 如果不将销售eVar与产 `addProductEvar` 品语法一起使用，则无需使用插件。

> [!NOTE] 此插件不替换产品条目中已存在的eVar。 它仅附加您使用此插件设置的值。 附加该产品已存在的eVar时请务必小心。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 对于要使用插件的任何启动规则，请添加一个具有以下配置的操作：
   * 扩展：常见分析插件
   * 操作类型：初始化addProductEvar
1. 保存更改并发布到规则

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 `s_gi`码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvar v1.0 */
s.addProductEvar=function(en,ev,ap){if("string"===typeof en&&"string"===typeof ev&&""!==ev)if(ap=ap||!1,this.products){var e=this.products.split(","),f=e.length;ap=ap?0:f-1;for(var a;ap<f;ap++)a=e[ap].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")?a[5]=a[5]+"|"+en+"="+ev:a[5]?a[5]=en+"="+ev:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=en+"="+ev),e[ap]=a.join(";");this.products=e.join(",")}else this.products=";;;;;"+en+"="+ev};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该 `addProductEvar` 插件使用以下参数：

* **`en`**（必需，字符串）:要添加到当前包含在products变量中的最后一个条目的eVar。 如果products变量为空，则插件将创建一个“空白”产品条目，其eVar值附加到条目末尾。
* **`ev`**（必需，字符串）:分配给eVar的值。
* **`ap`**（可选，布尔）:如果products变量当前包含多个产品条目，则值为true（或1）会将eVar添加到所**&#x200B;有&#x200B;**产品条目。  默认为false（或0），它只将eVar添加到products变量中**&#x200B;包含的&#x200B;**最后一个条目。

该 `addProductEvar` 插件不会返回任何内容。 而是将和参数中指定的eVar（和eVar值） `en` 添加 `ev` 到变 `products` 量。

## 示例

```js
// Set a merchandising eVar to blue on the last product. The output for the products variable is ";product1;3;300,;product2;2;122,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue");

// Set a merchandising eVar to blue on all products. The output for the products variable is ";product1;3;300;;eVar1=blue,;product2;2;122;;eVar1=blue,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue", true);

// Set multiple merchandising eVars to the last product in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium");
s.addProductEvar("eVar24", "women");
s.addProductEvar("eVar1", "red");

// Set multiple merchandising eVars to all products in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue|eVar23=medium|eVar24=women|eVar1=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar1=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium", true);
s.addProductEvar("eVar24", "women", true);
s.addProductEvar("eVar1", "red", true);

// If the products variable is not set, the plug-in creates an empty product string correctly delimited to the merchandising eVar. The output for the products variable is ";;;;;eVar1=blue"
s.addProductEvar("eVar1", "blue");
```

## 版本历史

### 1.0（2019年10月7日）

* 第一版。
