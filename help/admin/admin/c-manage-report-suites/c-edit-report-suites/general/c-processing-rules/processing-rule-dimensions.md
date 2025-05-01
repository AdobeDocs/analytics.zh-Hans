---
description: 可使用处理规则读取和写入的可用维度和量度。
subtopic: Processing rules
title: 可用于处理规则的维度
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: b53ef727adc563e05403c50d80bbd0c48bb8a054
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 13%

---

# 可用于处理规则的维度和量度

可使用处理规则读取和写入的可用维度和量度。

## 自定义值和上下文数据

| 值 | 读/写状态 | 描述 |
| --- | --- | --- |
| 自定义值 | 只读 | 在处理规则的操作中直接键入的自定义文本或值。 |
| 拼接值 | 只读 | 通过组合两个值创建的值。 例如，可以将渠道和页面名称结合起来创建子类别。 |

## 点击属性

| 属性 | 读/写状态 | 描述 |
| --- | --- | --- |
| 页面 URL | 读取+写入 | [页面URL](/help/components/dimensions/page-url.md)维度。 链接跟踪点击在到达处理规则之前剥离此维度。 如果使用处理规则重新插入页面URL值，则将点击视为[页面查看](/help/components/metrics/page-views.md)，而不是[页面事件](/help/components/metrics/page-events.md)。 Adobe建议在修改页面维度之前检查该维度中的值。 |
| 页面名称 | 读取+写入 | [页面](/help/components/dimensions/page.md)维度。 链接跟踪点击在到达处理规则之前剥离此维度。 如果使用处理规则重新插入页面值，则将点击视为[页面查看](/help/components/metrics/page-views.md)，而不是[页面事件](/help/components/metrics/page-events.md)。 Adobe建议在修改页面维度之前检查该维度中的值。 |
| 报告包 ID | 只读 | 执行处理规则的报表包。 此报表包可能与最初通过AppMeasurement发送的报表包不同，例如当使用VISTA规则时。 |
| AppMeasurement代码版本 | 只读 | 用于生成图像请求的AppMeasurement库版本。 |
| IP 地址 | 只读 | 访客的IP地址。 |
| 用户代理 | 只读 | 访客的用户代理。 |
| 反向链接 | 只读 | [推荐人](/help/components/dimensions/referrer.md)维度。 |
| 查询字符串参数 | 只读 | 当前URL中指定查询字符串参数的值。 |
| 引用查询字符串参数 | 只读 | 引用URL中指定查询字符串参数的值，如果不存在则为空字符串。 |
| 反向链接域 | 只读 | 反向链接URL的页面域，包括子域。 |
| 反向链接根域 | 只读 | 反向链接URL的页面域，不包括子域。 |
| 页面查询字符串 | 只读 | 当前URL中的所有查询字符串参数及其值。 |
| 引用查询字符串 | 只读 | 引荐URL中的所有查询字符串参数及其值。 |
| 页面路径 | 只读 | 当前URL的页面路径。 页面路径不包括协议、域或查询字符串参数。 |
| 页面域 | 只读 | 当前URL的页面域，包括子域。 页面域不包括页面路径或查询字符串参数。 |
| 页面根目录域 | 只读 | 当前URL的页面域，不包括子域。 |
| 客户视角 | 读取+写入 | 确定点击是否为移动后台点击的标记。 |

## 转化变量

| 变量 | 读/写状态 | 描述 |
| --- | --- | --- |
| eVar 1-250 | 读取+写入 | [eVar](/help/components/dimensions/evar.md)维度。 |
| 促销活动 | 读取+写入 | [跟踪代码](/help/components/dimensions/tracking-code.md)维度。 |
| 购买 ID | 读取+写入 | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)实现变量。 |
| 省/州 | 读取+写入 | [`state`](/help/implement/vars/page-vars/state.md)实现变量已停用。 |
| Zip | 读取+写入 | [邮政编码](/help/components/dimensions/zip-code.md)维度。 |
| 货币代码 | 读取+写入 | [`currencyCode`](/help/implement/vars/config-vars/currencycode.md)实现变量。 重要信息：如果将此变量设置为无效值，则将丢弃点击。 |
| 交易 ID | 读取+写入 | [`transactionID`](/help/import/data-sources/transactionid.md)实现变量。 |

>[!NOTE]
>Adobe不支持使用处理规则设置[`products`](/help/implement/vars/page-vars/products.md)实现变量。

## 流量变量

| 变量 | 读/写状态 | 描述 |
| --- | --- | --- |
| Prop 1-75 | 读取+写入 | [Prop](/help/components/dimensions/prop.md)维度。 |
| 层次结构 1-5 | 读取+写入 | [层次结构](/help/components/dimensions/hierarchy.md)维度。 |
| 服务器 | 读取+写入 | [服务器](/help/components/dimensions/server.md)维度。 |
| 渠道 | 读取+写入 | [网站区域](/help/components/dimensions/site-section.md)维度。 |

## 上下文变量

此报表包在以前的图像请求中看到的所有[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)。 如果处理规则未将上下文数据放置到其他变量中，则该数据将永久丢失。 有关用法示例，请参阅[将上下文数据变量复制到eVar](processing-rules-examples/processing-rules-copy-context-data.md)和[使用上下文数据变量设置事件](processing-rules-examples/processing-rules-copy-context-data-event.md)。

## 成功事件

处理规则可以设置事件，但无法将其读取为条件。 将规则操作下拉列表设置为&#x200B;**[!UICONTROL 设置事件]**&#x200B;以查看要递增的可用量度。

| 变量 | 读/写状态 | 描述 |
| --- | --- | --- |
| 订单数 | 仅写入 | [订单](/help/components/metrics/orders.md)量度。 |
| 购物车 | 仅写入 | [购物车](/help/components/metrics/carts.md)量度。 |
| 购物车查看 | 仅写入 | [购物车查看次数](/help/components/metrics/cart-views.md)量度。 |
| 结账 | 仅写入 | [结帐](/help/components/metrics/checkouts.md)指标。 |
| 购物车加货 | 仅写入 | [购物车添加](/help/components/metrics/cart-additions.md)量度。 |
| 购物车减货 | 仅写入 | [购物车移除](/help/components/metrics/cart-removals.md)量度。 |
| 事件 1-1000 | 仅写入 | [自定义事件](/help/components/metrics/custom-events.md)。 |
| 产品查看次数 | 仅写入 | [产品查看次数](/help/components/metrics/product-views.md)量度。 |

