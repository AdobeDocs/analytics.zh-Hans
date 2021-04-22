---
title: s_gi()
description: 创建和跟踪 AppMeasurement 实例。
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '341'
ht-degree: 100%

---

# s_gi

`s_gi()` 函数按报表包 ID 实例化或查找 AppMeasurement 的实例。AppMeasurement 会保持跟踪每个创建的实例，`s_gi()` 会为报表包返回现有实例（如果存在）。如果实例不存在，则会创建一个新实例。

## Adobe Experience Platform Launch 中的 s_gi()

Analytics 扩展可为您实例化和管理跟踪对象。但是，在配置 Adobe Analytics 扩展时，您还可以在[!UICONTROL 库管理]折叠面板中设置全局跟踪对象。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开[!UICONTROL 库管理]折叠面板，然后选择除[!UICONTROL 为我管理库]之外的任何单选按钮。

全局变量文本字段允许您设置自定义跟踪对象。其默认值为 `s`。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s_gi()

调用 `s_gi()` 函数以实例化跟踪对象。其唯一参数包含以逗号分隔的报表包 ID 字符串。报表包 ID 参数为必需参数。

>[!TIP]
>
>Adobe 建议将 `s` 变量用作跟踪对象。Adobe 在其文档、实施示例和插件中使用 `s`。但是，只要在网站中保持一致，可以使用任何变量。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>以下各部分和示例包含复杂的实施主题。完整测试您的实施并跟踪贵组织的](../../prepare/solution-design.md)解决方案设计文档[中的重要自定义项。

## 使用不同的跟踪对象管理多个实施

如果您实例化多个跟踪对象，则可以向不同的报表包发送不同的数据。这两个跟踪对象会相互独立地运作。

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

## 覆盖 s 对象后还原 AppMeasurement 变量

某些第三方工具可能还使用 JavaScript `s` 对象。如果意外覆盖了网站上的 `s` 对象，可以使用相同的 RSID 字符串参数调用 `s_gi` 以恢复所有被覆盖的变量和方法。

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

如果两个变量使用同一报表包引用同一 `s_gi()` 函数，则可以交替使用这些变量。

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
