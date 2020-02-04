---
title: s_gi()
description: 创建和跟踪AppMeasurement实例。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# s_gi

该函 `s_gi()` 数按报表包ID实例化或查找AppMeasurement的实例。 AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. 如果实例不存在，则会创建新实例。

## s_gi()

Analytics扩展为您实例化和管理跟踪对象。 但是，在配置Adobe Analytics扩展时，您也可以在“库管理” [!UICONTROL 折叠式] (Library Management)面板中设置全局跟踪对象。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开“ [!UICONTROL 库管理] ”折叠面板，然后选择除“为我管理库” [!UICONTROL 之外的任何单选按钮]。

全局变量文本字段允许您设置自定义跟踪对象。 Its default value is `s`.

## s_gi()在AppMeasurement和Launch自定义代码编辑器中

调用函 `s_gi()` 数以实例化跟踪对象。 其唯一参数包含以逗号分隔的报表包ID字符串。 报表包ID参数为必填。

> [!TIP] Adobe建议将该变 `s` 量用作跟踪对象。 Adobe在其 `s` 文档、实施示例和插件中使用。 但是，只要您的站点保持一致，您就可以使用任何变量。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!WARNING] 以下各节和示例包含复杂的实施主题。 彻底测试您的实施并跟踪贵组织的解决方案设计文档中的重 [要自定义项](../../prepare/solution-design.md)。

## 使用不同的跟踪对象管理多个实现

如果您实例化了多个跟踪对象，则可以向不同的报表包发送不同的数据。 这两个跟踪对象相互独立地操作。

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## 覆盖s对象后恢复AppMeasurement变量

某些第三方工具可能还使用JavaScript对 `s` 象。 如果意外覆盖了站 `s` 点上的对象，可以使用相同的RSID字符串 `s_gi` 参数调用以恢复所有被覆盖的变量和方法。

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## 使用多个变量引用同一跟踪对象

如果两个变量在同一报 `s_gi()` 表包中引用同一函数，则可以交替使用这些变量。

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
