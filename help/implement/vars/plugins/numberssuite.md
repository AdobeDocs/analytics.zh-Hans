---
title: Numbers Suite
description: 生成和处理数字以供在其他 JavaScript 变量中使用。
feature: Variables
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 94%

---

# Adobe 插件：Numbers Suite

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与贵组织的帐户管理员联系。他们可以为您安排与顾问的答疑会，以便您向顾问寻求帮助。

Numbers Suite 包含一系列 JavaScript 函数。具体包含以下插件：

* **`zeroPad`**：在数字的开头处添加特定数量的零。如果变量需要达到特定的位数，例如您要使用 JavaScript 日期对象，并且希望用两位数（而不是只用一位数）来格式化某个日期对应的月和日，则可以使用此插件。例如，采用 `01/09/2020` 格式而不是 `1/9/2020` 格式。
* **`randomNumber`**：生成具有特定位数的随机数。如果您部署第三方标签并希望获取用于搜索缓存的随机数，此插件非常有用。
* **`twoDecimals`**：将数字四舍五入到其最接近的百分位值。此插件可用于处理货币，允许您将数字四舍五入为有效货币值。

## 使用Web SDK或Adobe Analytics扩展安装此插件

Adobe 提供了一个扩展，通过该扩展，您可以使用一些常用插件。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL 目录]按钮
1. 安装并发布[!UICONTROL 常用 Analytics 插件]扩展
1. 如果还没有任何扩展，请使用以下配置创建一个标签为“初始化插件”的规则：
   * 条件：无
   * 事件：核心 - 已加载的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常用 Analytics 插件
   * 操作类型：初始化 Numbers Suite
1. 保存并发布对上述规则所做的更改。

## 使用自定义代码编辑器安装此插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
1. 单击所需的属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL 使用自定义代码配置跟踪]折叠面板，这会显示[!UICONTROL 打开编辑器]按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存并发布对此 Analytics 扩展所做的更改。

## 使用 AppMeasurement 安装此插件

在实例化（使用 [`s_gi`](../functions/s-gi.md)）Analytics 跟踪对象后，将以下代码复制并粘贴到 AppMeasurement 文件中的任意位置。在您的实施中保留代码的注释和版本号可帮助 Adobe 对任何潜在问题进行疑难解答。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

`zeroPad` 函数使用以下参数：

* **num**（必需，整数）：要填充的数字。如果此参数的值含小数，则此函数会对该值进行四舍五入。
* **nod**（必需，整数）：最终返回值的位数。如果要填充的数字的位数少于要填充的位数，则此插件会在 `num` 参数的开头处添加相应数量的零。

`randomNumber` 函数使用以下参数：

* **nod**（可选，整数）：要生成的随机数的位数。最大值为 17 位。默认值为 10 位。

`twoDecimals` 函数使用以下参数：

* **val**（必需，数字）：要将其四舍五入到最接近的百分位值的数字（由字符串或数字对象表示）。

## 返回结果

* **zeroPad** 函数会返回一个等于 `num` 参数的字符串，但会在其值的开头处添加特定数量的零，以确保返回值具有正确位数。
* **randomNumber** 函数会返回一个等于具有所需位数的随机数的字符串。
* **twoDecimals** 函数会返回一个已四舍五入到最接近的百分位值的数字对象。

## 示例调用

### zeroPad 示例

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber 示例

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimals 示例

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## 版本历史记录

### 1.0（2019 年 5 月 25 日）

* 第一版。
