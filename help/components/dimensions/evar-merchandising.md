---
title: eVar（“促销”维度）
description: 与产品维度关联的自定义变量。
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 79%

---

# eVar (Merchandising)

*此帮助页介绍推销eVar如何作为[维度](overview.md)使用。 有关如何实施推销eVar的信息，请参阅《实施用户指南》中的[eVar （促销变量）](/help/implement/vars/page-vars/evar-merchandising.md)。*

有关促销 eVar 如何工作的详细讨论，请参阅[促销 eVar 和产品查找方法](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)。

在衡量外部营销活动或外部搜索词的成功时，您通常希望为发生的任何成功事件接收点数。 例如，如果客户单击电子邮件营销活动中的链接来访问您的网站，则因此进行的所有购买都应计入该营销活动。

当客户查找多个项时，因内部搜索或按类别浏览所促成的事件又该如何呢？ 例如，某个客户在您的站点中搜索 `"goggles"`，并将其加入购物车中：

![护目镜示例](assets/merch-example-goggles.png)

在结帐之前，客户又搜索 `"winter coat"`，并将一件羽绒服加入购物车内：

![外套示例](assets/merch-example-coat.png)

当访客完成此次购买时，您将进行内部搜索 `"winter coat"`，以计入购买一对护目镜（假设 eVar 使用默认的“最新”分配）。 虽然这样对 `"winter coat"` 关键字不错，但不利于做出营销决策：

| 内部搜索词 | 收入 |
|---|---|
| 冬季外套 | $157 |

## 推销变量如何解决此问题

推销 eVar 允许您在成功事件发生时将 eVar 的当前值分配给某个产品。 此值将始终与该产品绑定，即使这个特定的 eVar 以后设置了一个或多个新的值也不例外。

如果前一示例中 eVar 启用了推销，则搜索术语 `"goggles"` 将与“雪地护目镜”绑定，而搜索术语 `"winter coat"` 将与“羽绒服”绑定。 推销 eVar 会在产品级别分配收入，所以每个术语都会收到与其关联产品的收入额信用：

| 内部搜索词 | 收入 |
|---|---|
| 冬季外套 | $119 |
| 护目镜 | $38 |

有关实施说明，请参阅[推销 eVar](/help/implement/vars/page-vars/evar-merchandising.md)。

## 有关推销变量的实例

不建议将[实例](../metrics/instances.md)量度用于推销变量。

* 对于使用产品语法的推销变量，实例根本不会增加。
* 对于使用转化变量语法的推销变量，每次设置 eVar 时都会计算实例。 但是，它归因于维度项目 `"None"`，除非在同一次点击中发生以下所有情况：
   * 为推销 eVar 设置一个值。
   * 使用一个值定义了 `products` 变量。
   * 已设置捆绑事件。

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

由于转化变量语法的大多数用例需要不同点击上的 eVar 和产品变量，因此，使用“实例”量度是不现实的。
