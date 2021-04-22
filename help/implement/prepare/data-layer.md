---
title: 创建数据层
description: 了解 Analytics 实施中的数据层，以及如何在 Adobe Analytics 中使用它来映射变量。
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '479'
ht-degree: 100%

---

# 创建数据层

数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。

## 先决条件

[创建解决方案设计文档](solution-design.md) - 贵组织务必要根据跟踪要求进行调整，这一点很重要。在联系组织中的开发团队之前，确保您已准备了解决方案设计文档。

## 工作流

使用数据层实施 Adobe Analytics 时通常遵循以下步骤：

1. **与网站开发团队合作实施数据层**：网站开发团队主要负责确保使用正确的值填充数据层对象。与您的网站开发团队一起检查此页面，以确保各团队的期望是一致的。

   >[!NOTE]
   >
   > 是否遵循 Adobe 推荐的数据层规范是可选的。如果您已经有一个数据层，或者选择不遵循 Adobe 提供的规范，请确保贵组织与要遵循的规范保持一致。
1. **使用浏览器控制台验证数据层**：创建数据层后，您可以使用任意浏览器的开发人员控制台来验证数据层是否可正常使用。在大多数浏览器中，您都可以使用 `F12` 键打开开发人员控制台。`digitalData.page.pageInfo.pageID` 是一个示例变量值。
1. **使用 Adobe Experience Platform Launch 将数据层对象映射到 Launch 数据元素**：在 Launch 中创建数据元素，并将其映射到在数据层中列出的 JavaScript 属性。
1. **使用 Launch 中的 Adobe Analytics 扩展将数据元素映射到 Analytics 变量**：根据您的解决方案设计文档，将每个数据元素分配给相应的 Analytics 变量。

## 规范

Adobe 建议遵循由 [Customer Experience Digital Data Community Group](https://www.w3.org/community/custexpdata/) 制定的 [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) 规范。请阅读以下几节内容，以了解数据层元素如何与 Adobe Analytics 交互。

建议使用的总数据层对象是 `digitalData`。以下示例使用示例数据列出了一个比较全面的数据层 JSON 对象：

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

有关每个对象和子对象的详细信息，请参阅 [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) 报表。并非所有网站都会使用所有对象，例如，如果您托管新的网站，那么就不太可能使用 `digitalData.product` 对象数组。

数据层是可扩展的；如果贵组织有特定需求，则可以在数据层中包含相应对象以满足这些需求。

## 设置数据层值

数据层通常会在服务器端生成，并引用构建网站内容时所使用的相同对象。根据在组织的[解决方案设计文档](solution-design.md)中设定的跟踪需求建立网站数据层。

## 后续步骤

[将数据层对象映射到数据元素](../launch/layer-to-elements.md)：在 Adobe Experience Platform Launch 中使用网站的数据层。
