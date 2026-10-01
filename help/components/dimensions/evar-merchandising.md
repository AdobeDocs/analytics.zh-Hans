---
title: eVar（“促销”维度）
description: 与产品维度关联的自定义变量。
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: 'https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '2343'
ht-degree: 4%
---
# eVar (Merchandising)

>[!BEGINSHADEBOX]

*此帮助页介绍推销eVar如何作为[维度](overview.md)使用。 有关如何实施推销eVar的信息，请参阅《实施用户指南》中的[eVar （促销变量）](/help/implement/vars/page-vars/evar-merchandising.md)。*

>[!ENDSHADEBOX]

推销eVar的工作方式与标准eVar类似，不同之处在于每个产品都有自己的副本。 持久性、分配和到期的工作方式都相同，但每种产品的情况各不相同。 标准eVar会为每个访客保留一个持久值，每个访客都会获得每个成功事件的信用。 推销eVar为每个产品保留一个持久值，该值接收该产品成功事件的信用：

* 产品A → `eVar1` = `value A`
* 产品B → `eVar1` = `value B`

每个产品的值只能在包含该产品的点击中进行设置或更改。 设置后，该值将持续存在，直到它过期并仅接收该产品成功事件的信用。 更改产品A的值对产品B没有影响。

推销eVar只能与[`products`](/help/implement/vars/page-vars/products.md)变量一起使用。 未捆绑到产品的推销eVar值不会获得任何点数。 每个推销eVar中，不含产品的点击上的成功事件都归因于`"None"`。

>[!TIP]
>
>要将持久值绑定到产品以外的维度，请考虑在Customer Journey Analytics中使用[[!UICONTROL 绑定维度]](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/persistence#binding-dimension)。

## 为何使用推销eVar

当单个值不应接收访客所购买所有产品的点数时，为每个产品保留一个单独值很重要。 标准eVar非常适用于外部营销活动或外部搜索词，在这些搜索词中，一个值应该接收发生的任何成功事件的点数。 例如，如果客户单击电子邮件营销活动中的链接来访问您的网站，则因此进行的所有购买都应计入该营销活动。

内部搜索和类别浏览是不同的，因为访客经常使用它们查找多个产品，每个产品查找的方式不同。 例如，某个客户在您的站点中搜索 `"goggles"`，并将其加入购物车中：

![护目镜示例](assets/merch-example-goggles.png)

在结帐之前，客户又搜索`"winter coat"`，然后为其购物车添加了一件羽绒服：

![外套示例](assets/merch-example-coat.png)

当访客完成此次购买时，内部搜索词`"winter coat"`将收到整个订单（包括护目镜）的点数，因为这是eVar的最新值(默认分配为[!UICONTROL 最近（最后一个）])。 搜索词`"goggles"`未获得任何信用，即使它导致了部分购买：

| 内部搜索词 | 收入 |
| --- | --- |
| 冬季外套 | $157 |

## 推销eVar如何解决此问题

如果前一示例中为eVar启用了推销，则搜索词`"goggles"`将绑定到雪地护目镜，而搜索词`"winter coat"`将绑定到羽绒服。 推销eVar会在产品级别分配收入，因此每个术语都会收到与其绑定的产品的收入额信用：

| 内部搜索词 | 收入 |
| --- | --- |
| 冬季外套 | $119 |
| 护目镜 | $38 |

## 绑定和分配的工作原理

促销eVar依赖于三个概念：

* **绑定**：产品与eVar值之间的关联。 每种产品都保留着对每种推销eVar的捆绑。 与标准eVar值类似，捆绑在之后的点击中持续存在，直到它过期为止。 例如，如果在以后页面上购买某个产品时，与产品页面上的产品绑定的值仍会获得点数，而无需再次设置该值。 值如何到达产品取决于下面描述的eVar语法。
* **分配**： [!UICONTROL 分配]设置确定当新值尝试绑定到&#x200B;**已绑定**&#x200B;的产品时会发生什么情况。 系统会分别评估每个产品的分配，因此捆绑到不同产品的推销eVar值永远不相互竞争。
  * **[!UICONTROL 原始值（第一个）]**：保留现有的绑定。 在捆绑到期之前，将忽略该产品的新值。
  * **[!UICONTROL 最近（最后一个）]**：产品已重新绑定到新值。
* **过期**： [!UICONTROL 过期时间]设置确定绑定何时结束。 每个产品的捆绑都有各自的过期时间，从捆绑该产品时开始计数。 例如，在[!UICONTROL 周]到期的情况下，如果产品A在星期一捆绑，产品B在星期三捆绑，则产品A的捆绑在下一星期一到期，而产品B的捆绑在下一星期三到期。 捆绑过期后，产品将不再具有该eVar的值，就像标准eVar过期后没有值一样。 该产品的成功事件将归因于`"None"`，直到再次捆绑该产品为止。

每个推销eVar都使用[报表包设置](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)中的[!UICONTROL 推销]设置中设置的两种语法之一。 语法确定值如何到达产品：

* **[产品语法](#product-syntax)**：该值直接在`products`变量中的每个产品上设置，并在点击时绑定到该产品。
* **[转化变量语法](#conversion-variable-syntax)**：该值在eVar中设置，并像标准eVar值一样持续存在。 它会绑定到同一点击或包含捆绑事件的更高点击上的产品。

两种语法使用上述相同的绑定、分配和到期行为。 它们的不同之处在于：

| | 产品语法 | 转化变量语法 |
| --- | --- | --- |
| 设置值的位置 | 在每个产品的[`products`](/help/implement/vars/page-vars/products.md)变量中 | 在[`eVar`](/help/implement/vars/page-vars/evar-merchandising.md)本身中，与标准eVar相同 |
| 捆绑发生时 | 在产品上设置值的任何点击上 | 在包含产品和已配置的捆绑事件的点击上 |
| 每次点击的值 | 每个产品可以具有不同的值 | 捆绑点击中的每个产品都会收到相同的值 |
| 实施工作 | 较高 | Lower |

## 产品语法

使用产品语法，在`products`变量中的每个产品上设置eVar值。 在`products`字符串中，产品的最后一个分号后面的值是它的促销eVar。 有关完整语法，请参阅[使用产品语法实施](/help/implement/vars/page-vars/evar-merchandising.md#implement-using-product-syntax)。

该值会直接绑定到该点击上的产品。 未使用捆绑事件。 后续包含产品的点击（例如购物车添加或购买）不需要重复该值。 由于每个产品都有自己的值，因此，当&#x200B;**相同点击**&#x200B;中的产品需要&#x200B;**不同的**&#x200B;值时，产品语法是唯一的选项。

+++示例：同一产品接收两个值

| 点击 | `products` | `events` |
| --- | --- | --- |
| 1 | `;12345;;;;eVar1=internal keyword search` | |
| 2 | `;12345;;;;eVar1=internal campaign` | |
| 3 | `;12345;1;50` | `purchase` |

* **[!UICONTROL 原始值（第一个）]**：忽略产品`12345`的点击2。 购买已贷记到`internal keyword search`。
* **[!UICONTROL 最近（最后一个）]**：点击2重新绑定产品`12345`。 购买已贷记到`internal campaign`。

+++

+++示例：两个产品接收不同的值

| 点击 | `products` | `events` |
| --- | --- | --- |
| 1 | `;productA;;;;eVar1=value A` | |
| 2 | `;productB;;;;eVar1=value B` | |
| 3 | `;productA;1;50,;productB;1;30` | `purchase` |

每个产品都保留其自身的捆绑，因此本例中的分配设置不起作用。 `value A`接收产品A收入的点数，`value B`接收产品B收入的点数。 这两个值都会收到一个订单，因为该订单包含与每个值绑定的产品。

+++

+++示例：具有相同ID和不同值的产品

访客购买了一件中号蓝色T恤和一件大号红色T恤，两者具有父产品ID `tshirt123`，且`eVar10`捕获了子SKU：

```js
s.events = "purchase";
s.products = ";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

每个子SKU都收到其自己的`tshirt123`实例的点数。

+++

取舍是，每当应该进行捆绑时，产品语法需要每个产品上的完整值字符串。 对于产品查找方法（通常同时使用多个eVar），字符串如下所示：

```js
s.products = ";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

查找方法应仅在访客与产品交互后获得点数，因此此字符串通常在产品详细信息页面或购物车添加上设置，而不是在搜索结果页面上设置。 为此，开发人员必须：

* 将查找方法详细信息从查找方法页面传送到产品详细信息页面，或在购物车添加从结果页面触发时使其可用。
* 组合完整的`products`字符串，且无语法错误。

转化变量语法可避免这两种要求。

## 转化变量语法

使用转化变量语法，此值是在eVar本身中设置的：

```js
s.eVar1 = "internal keyword search";
```

eVar充当&#x200B;*临时区域*。 eVar中设置的值会保留在该处，直到捆绑事件将其捆绑到点击中的产品。 绑定分为两个阶段：

1. **暂存**：设置eVar时，其值在后续点击中持续存在，直到它过期。 此保留值是[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)中的`post_evar`列。 对于使用转化变量语法的促销eVar，暂存值&#x200B;**始终反映发送的最近值**，无论[!UICONTROL Allocation]设置如何。 每个新值都会替换以前转移的值。
1. **捆绑**：当点击包含产品和配置的[!UICONTROL 促销捆绑事件]时，暂存值将捆绑到该点击上的每个产品。 如果产品已绑定，[!UICONTROL 分配]将确定是否用新值替换现有绑定。 已绑定的产品会将其值保留为[!UICONTROL 原始值（第一个）]，或重新绑定为[!UICONTROL 最近（最后一个）]。

如果eVar、`products`变量和捆绑事件均在同一点击中设置，则暂存和捆绑将同时发生。 新值将立即绑定到该点击上的产品。

在没有捆绑事件的产品旁设置eVar不会将该值捆绑到该产品。 暂存值在捆绑到产品之前不接收任何信用。

### 捆绑事件的功能

捆绑事件是触发器，它告知Adobe将暂存值捆绑到点击中的产品。

* 捆绑事件可以是标准或自定义成功事件、跟踪代码（[!UICONTROL 促销活动事件]）或eVar。 prop对绑定没有影响。
* 您可以配置多个捆绑事件，如[!UICONTROL 产品查看事件]、[!UICONTROL 购物车添加事件]和[!UICONTROL 购买事件]。 如果这些事件中的任何一个位于包含产品的点击上，则暂存值将绑定到该点击上的每个产品。
* 默认情况下([!UICONTROL All])，只要任何其他事件或eVar与某个产品处于同一点击中，就会发生捆绑。 如果未显式选择绑定事件，则使用[!UICONTROL All]。 使用[!UICONTROL All]，在包含产品的点击上设置eVar将始终触发该点击的绑定。 在之前的点击中暂存的值会在下一次点击时绑定，其中包含产品和任何其他事件或eVar。

+++示例：与捆绑事件绑定

请考虑以下点击：

```js
// Hit 1
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";

// Hit 2
s.products = ";sandal123";
s.events = "prodView";
```

如果`prodView`是两个eVar的捆绑事件，则点击2将`internal keyword search` (`eVar1`)和`sandals` (`eVar2`)捆绑到`sandal123`。 如果eVar未将`prodView`列为捆绑事件，则不会发生针对该eVar的捆绑。

+++

+++示例：按产品评估分配

| 点击 | `eVar1` | `products` | `events` |
| --- | --- | --- | --- |
| 1 | `value A` | | |
| 2 | | `;productA,;productB` | 捆绑事件 |
| 3 | `value B` | | |
| 4 | | `;productA` | 捆绑事件 |
| 5 | | `;productA;1;50,;productB;1;30` | `purchase` |

在点击3之后，使用任一分配设置暂存值(`post_evar1`)为`value B`。

* **[!UICONTROL 原始值（第一个）]**：忽略产品A的点击4，因为产品A已绑定。 这两种产品都与`value A`保持绑定，后者接收所有购买点数。
* **[!UICONTROL 最近（最后一个）]**：点击4将产品A重新捆绑到`value B`。 产品B不在点击4中，因此它保持绑定到`value A`。 产品A的购买点数归入`value B`，产品B的购买点数归入`value A`。

如果只有一次绑定尝试（例如仅点击1、2和5），则两个设置都会产生相同的结果。 仅当已绑定的产品收到另一次绑定尝试时，分配才重要。

+++

## 最佳实践：产品查找方法

大多数零售网站都受益于跟踪以下产品查找方法，每种方法都作为促销eVar：

* 内部搜索关键词（例如，`eVar2`）
* 内部营销活动跟踪代码（例如，`eVar3`）
* 促销或浏览类别（例如，`eVar4`）
* 交叉销售链接（例如，`eVar5`）
* 一种总体产品查找方法，eVar比较所有方法，包括诸如产品页面的外部链接等方法（例如，`eVar1`）

当访客使用一种方法时，将另一种查找方法eVar设置为“非”值。 否则，未使用方法的较早值可能会收到通过其他方法找到的产品的点数。 例如，在结果页面上搜索“凉鞋”：

```js
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";
s.eVar3 = "non-internal campaign";
s.eVar4 = "non-browse";
s.eVar5 = "non-cross-sell";
```

使用转化变量语法，开发人员只能设置简单值，例如prop中的搜索词，并且实施中的逻辑可以填充推销eVar。 不需要在页面之间传递任何内容，也不需要内置到`products`字符串中。 在进行绑定的点击上仍需要`products`变量。

Adobe建议对产品查找方法eVar进行以下设置：

| 设置 | 数值 |
| --- | --- |
| [!UICONTROL 分配] | [!UICONTROL 原始值（第一个）] |
| [!UICONTROL 过期时间] | 在自动移除之前，产品在购物车中停留的时间，如使用[!UICONTROL 自定义]的14天或30天。 如果购物车没有限制，请使用[!UICONTROL 购买]。 |
| [!UICONTROL Type] | [!UICONTROL 文本字符串] |
| [!UICONTROL 启用促销] | [!UICONTROL 已启用] |
| [!UICONTROL 促销] | [!UICONTROL 转化变量语法] |
| [!UICONTROL 促销捆绑事件] | [!UICONTROL 产品查看事件]、[!UICONTROL 购物车添加事件]和[!UICONTROL 购买事件] |

有关每个设置的说明，请参阅管理员指南中的[转化变量](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)。

+++为什么原始值（第一个）而不是最近（最后一个）

访客经常会重新找到他们已经查看或添加到购物车中的产品。 例如：

1. 访客搜索“凉鞋”，并从结果页面将`sandal123`添加到购物车。 产品捆绑到`internal keyword search`。
1. 三天后，该访客浏览到&#x200B;**女性>鞋子>凉鞋** (`eVar1` = `browse`)，再次查看`sandal123`，然后购买它。

通过[!UICONTROL 最近（最后一个）]，步骤2中的产品视图将`sandal123`重新绑定到`browse`，然后接收购买点数。 最初找到产品的方法不接收任何产品。

使用[!UICONTROL 原始值（第一个）]时，将忽略步骤2中的绑定尝试，`internal keyword search`将保留信用。

如果访客从未购买过产品，则过期会删除绑定，因此访客使用的下一个查找方法可以绑定到产品。 这就是为什么[!UICONTROL 过期时间]应与产品在购物车中的停留时间相匹配。

+++

## 有关促销eVar的实例

不建议将默认[实例](../metrics/instances.md)量度用于促销变量。

* 对于使用产品语法的促销变量，实例根本不会增加。
* 对于使用转化变量语法的促销变量，每次设置 eVar 时都会计算实例。 但是，实例归因于维度项`"None"`，除非在同一次点击中发生以下所有情况：
  * 为促销 eVar 设置一个值。
  * 使用一个值定义了 `products` 变量。
  * 已设置捆绑事件。

由于转化变量语法的大多数用例需要不同点击上的eVar和products变量，因此默认的“实例”量度不太现实。

要为使用转化变量语法发送的每个值计算实例，请将&#x200B;**最近联系** [归因模型](/help/analyze/analysis-workspace/attribution/overview.md)应用于实例量度。 归因模型使用每次点击时发送的值，而不是暂存值或产品捆绑。 回顾窗口并不重要，因为无论eVar的分配设置如何，“最近联系”都会计入发送该点击的每个值。

![归因选择](assets/attribution-select.png)
