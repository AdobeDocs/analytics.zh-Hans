---
title: list
description: 在同一点击中保留多个值的自定义变量。
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 74%

---

# list

列表变量是自定义变量，您可以根据需要随意使用。它们的工作方式与 eVar 类似，只是它们可以在同一点击中包含多个值。列表变量没有字符限制。

请确保在[解决方案设计文档](../../prepare/solution-design.md)中记录如何使用每个列表变量及其逻辑。

>[!NOTE]
>
>列表变量根据[报表包设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中的[!UICONTROL 最大值]设置存储每位访客的最新值。 最多支持250个值。 如果唯一值的数量超过[!UICONTROL 最大值]设置所允许的数量，则最早的值不会归属于量度。

## 在报告包设置中设置列表变量

确保先在报告包设置中配置每个列表变量，然后再在实施中使用它们。请参阅管理员指南中的[转化变量](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)。此步骤适用于所有实现方法。

## 使用 Web SDK 的列表变量

如果使用&#x200B;[**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，则列表变量使用`xdm._experience.analytics.customDimensions.lists.list1.list[]`到`xdm._experience.analytics.customDimensions.lists.list3.list[]`的XDM字段。 每个数组元素含有一个包含每个字符串的 `"value"` 对象。 无需提供分隔符；Adobe数据收集服务器会自动检测并在[报表包设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中包含正确的分隔符集。

```json
"xdm": {
  "_experience": {
    "analytics": {
      "customDimensions": {
        "lists": {
          "list1": {
            "list": [
              {
                "value": "Example value 1"
              },
              {
                "value": "Example value 2"
              },
              {
                "value": "Example value 3"
              }
            ]
          }
        }
      }
    }
  }
}
```

>[!NOTE]
>
>除了每个 `list[]` 数组中的 `value` 对象外，Adobe XDM 架构还包含 `key` 对象。当向 Adobe Analytics 发送数据时，Adobe 不使用这些 `key` 对象。

如果使用&#x200B;[**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则列表变量使用`data.__adobe.analytics.list1` - `data.adobe.analytics.list3`以下AppMeasurement语法。 确保在[报告包设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中使用正确的分隔符集。

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## 使用 Adobe Analytics 扩展程序的列表变量

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Analytics 扩展代码编辑器中的 s.list1 – s.list3

每个列表变量都是一个字符串，其中包含特定于贵组织的自定义值。此变量没有最大字节数；但是，每个单独值的最大限制为255字节。 在[报告包设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中设置变量时，将会确定使用的分隔符。 在分隔多个项目时不要使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>如果在同一点击中设置重复值，Adobe 会删除这些值的所有重复实例。例如，如果设置 `s.list1 = "Brick,Brick";`，则报告中会计入一个实例。

## 比较列表属性与列表变量

列表属性和列表变量都可以在同一点击中包含多个值。但是，这两种变量类型之间有几个关键区别。

* 任何 prop 都可以成为列表属性。如果每个 prop 都是列表属性，则实际上最多可以拥有 75 个列表属性。只有 3 个列表变量可用。
* 对于整个变量，列表属性具有 100 字节的限制。列表变量中每个值的长度限制为 255 字节，没有总字节限制。
* 列表属性不会在设置的点击之外继续存在。列表变量具有您需要的任何过期设置。但是，通过[报告时间处理](/help/components/vrs/vrs-report-time-processing.md)，您可以将自定义属性同时应用于列表属性和列表变量。
