---
title: 数字套件
description: 生成和处理数字以用于其他JavaScript变量。
translation-type: tm+mt
source-git-commit: cae119fab9756bd31f6d835000db0a068cb87834

---


# Adobe插件：数字套件

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics的使用中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

Numbers套件包含一系列JavaScript函数。 它包含以下插件：

* **`zeroPad`**:在数字的开头添加一个特定数目的零。 如果变量需要一定数字，例如您使用JavaScript日期对象，并且希望用两位数（而不是只用一位数）来格式化日期的月份和日期，则此插件非常有用。 例如，`01/09/2020`而不是`1/9/2020`。
* **`randomNumber`**:生成具有特定数字数的随机数。 如果您部署第三方标记并希望获得缓存破坏随机数，则此插件非常有用。
* **`twoDecimals`**:把一个数字绕到衣橱第100号。 此插件可用于货币用途，允许您将数字舍入为有效货币值。

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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用增效工具

该方 `zeroPad` 法使用以下参数：

* **num** (required, integer):要添加的数字。 如果此参数包含小数，则该方法将舍入此参数的值。
* **nod** （必需，整数）:最终返回值中的位数。 如果要填充的数字的位数少于要填充到的数字的位数，则插件会将零添加到参数的开 `num` 头。

该方 `randomNumber` 法使用以下参数：

* **nod** （可选，整数）:要生成的随机数中的数字数。 最大值为17位。 默认值是10位。

该方 `twoDecimals` 法使用以下参数：

* **val** (required, number):要舍入到最接近的百分之一的数字（由字符串或数字对象表示）。

## 返回结果

* **zeroPad**`num` 方法返回一个与参数相等的字符串，但在其值的开头加上特定数目的零，这可确保返回值具有正确的位数。
* randomNumber **方法返回一个字符串** ，该字符串等于具有所需数字数的随机数。
* twoDecimals **** 方法返回一个舍入到最接近的百分之一的数字对象。

## 示例调用

### zeroPad示例

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### randomNumber示例

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### twoDecimals示例

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## 版本历史

### 1.0（2019年5月25日）

* 第一版。
