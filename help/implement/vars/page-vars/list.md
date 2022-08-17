---
title: list
description: 在同一点击中保留多个值的自定义变量。
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: e8a6400895110a14306e2dc9465e5de03d1b5d73
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 62%

---

# 列表

列表变量是自定义变量，您可以根据需要随意使用。它们的工作方式与 eVar 类似，只是它们可以在同一点击中包含多个值。列表变量没有字符限制。

确保在[解决方案设计文档](../../prepare/solution-design.md)中记录如何使用每个列表变量及其逻辑。

>[!NOTE]
>
>列表变量存储每个访客最近的 250 个值。如果给定访客的唯一值超过 250 个，则最早的值不会归属于量度。

## 在报表包设置中设置列表变量

确保先在报表包设置中配置每个列表变量，然后再在实施中使用它们。请参阅《管理员指南》中的[转化变量](/help/admin/admin/conversion-var-admin/list-var-admin.md)。此步骤适用于所有实施方法。

>[!NOTE]
>
>使用Web SDK中映射的字段实施的列表变量使用逗号分隔符(“`,`&#39;)。

## 使用Web SDK列出变量

列表变量包括 [已映射Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM字段下 `_experience.analytics.customDimensions.lists.list1.list[]` to `_experience.analytics.customDimensions.lists.list3.list[]`. 每个数组元素都包含 `"value"` 包含每个字符串的对象。 例如，以下XDM对象填充了 `list1` 变量 `"Example value 1,Example value 2,Example value 3"`.

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

如果贵组织需要使用不同于逗号(“`,`“)，您可以将整个列表字符串（包括所需的分隔符）传递到自定义XDM字段。 确保将列表变量配置为在 [报表包设置](/help/admin/admin/conversion-var-admin/list-var-admin.md).

```json
"xdm": {
    "custom_object": {
        "custom_path": {
            "custom_listvar": "Example value 1|Example value 2|Example value 3"
        }
    }
}
```

然后，您可以：

* 将自定义XDM字段映射到Adobe Experience Edge中的所需列表变量；或
* 创建一个处理规则，以使用上下文数据变量覆盖所需的列表变量。 请参阅 [将其他XDM字段映射到Analytics变量](../../aep-edge/variable-mapping.md#mapping-other-xdm-fields-to-analytics-variables).

## 使用Adobe Analytics扩展列出变量

Adobe Analytics扩展中没有可使用此变量的专用字段。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.list1 - s.list3

每个列表变量都是一个字符串，其中包含特定于贵组织的自定义值。它们没有字节数上限；但是，单个值的最大长度为 255 字节。在 [报表包设置](/help/admin/admin/conversion-var-admin/list-var-admin.md). 在分隔多个项目时不要使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>如果在同一点击中设置重复值，Adobe 会删除这些值的所有重复实例。例如，如果设置 `s.list1 = "Brick,Brick";`，则报表中会计入一个实例。

## 比较列表属性与列表变量

列表属性和列表变量都可以在同一点击中包含多个值。但是，这两种变量类型之间有几个关键区别。

* 任何 prop 都可以成为列表属性。如果每个 prop 都是列表属性，则实际上最多可以拥有 75 个列表属性。只有 3 个列表变量可用。
* 对于整个变量，列表属性具有 100 字节的限制。列表变量中每个值的长度限制为 255 字节，没有总字节限制。
* 列表属性不会在设置的点击之外继续存在。列表变量具有您需要的任何过期设置。但是，通过[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)，您可以将自定义属性同时应用于列表属性和列表变量。
