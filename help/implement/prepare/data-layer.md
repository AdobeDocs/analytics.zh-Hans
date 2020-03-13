---
title: 创建数据层
description: 了解 Analytics 实施中的数据层，以及如何在 Adobe Analytics 中使用它来映射变量。
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# 创建数据层

数据层是站点上JavaScript对象的框架，其中包含实施中使用的所有变量值。 它允许在您的实施中更好地控制和维护。

## 先决条件

[创建解决方案设计文档](solution-design.md) -组织必须根据跟踪要求保持一致。 在与组织内的开发团队接洽之前，请确保您已准备好解决方案设计文档。

## 工作流

使用数据层实施Adobe Analytics通常遵循以下步骤：

1. **与站点开发团队合作实施数据层**:站点开发团队主要负责确保数据层对象填充有正确的值。 与您的站点开发团队一起查看此页面，以确保各团队之间的期望一致。
   > [!NOTE] 遵循Adobe推荐的数据层规范是可选的。 如果您已有数据层，或者选择不遵循Adobe的规范，请确保您的组织符合要遵循的规范。
2. **使用浏览器控制台验证数据层**:创建数据层后，您可以使用任何浏览器的开发人员控制台验证它是否在工作。 您可以使用该键在大多数浏览器中打开开发人员 `F12` 控制台。 示例变量值为 `digitalData.page.pageInfo.pageID`。
3. **使用Adobe Experience Platform Launch将数据层对象映射到启动数据元素**:在Launch中创建数据元素，并将其映射到数据层概述的JavaScript属性。
4. **使用Launch中的Adobe Analytics扩展将数据元素映射到Analytics变量**:根据您的解决方案设计文档，将每个数据元素分配给相应的Analytics变量。

## 规范

Adobe建议遵循客 [户体验数字数据社区组概述的](https://www.w3.org/2013/12/ceddl-201312.pdf) “客 [户体验数字数据层”](https://www.w3.org/community/custexpdata/)。 使用以下几节了解数据层元素如何与Adobe Analytics交互。

建议使用的总体数据层对象是 `digitalData`。 以下示例列出了一个包含示例值的比较全面的数据层JSON对象：

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
            subCategory1: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product1: {
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    },
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
    event1: {
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    component1: {
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    user1: {
        segment: "Premium membership",
        profile1: {
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
        }
    },
    privacy: {
        accessCategories1: {
            categoryName: "Default",
            domains: "adobedtm.com"
        }
    },
    version: "1.0"
}
```

有关每 [个对象和子对象的详细信息](https://www.w3.org/2013/12/ceddl-201312.pdf) ，请使用“客户体验数字数据层”报告。 并非所有网站都使用所有对象；例如，如果您托管新闻站点，则不太可能使用该对 `digitalData.product` 象。

数据层是可扩展的；如果您的组织有特定要求，则可以在数据层中包含对象以满足这些需求。

## 设置数据层值

数据层通常会生成服务器端，引用构建站点内容时所用的相同对象。 根据组织的解决方案设计文档中设置的跟踪要求建立站 [点的数据层](solution-design.md)。

## 后续步骤

[将数据层对象映射到数据元素](../launch/layer-to-elements.md):在Adobe Experience Platform Launch中使用站点的数据层。
