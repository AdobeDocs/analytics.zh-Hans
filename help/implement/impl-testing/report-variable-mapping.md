---
description: 下表显示报表到变量的映射或报表或映射中使用的报表和变量。
keywords: Analytics 实施
seo-description: 下表显示报表到变量的映射或报表或映射中使用的报表和变量。
seo-title: 报告到变量映射
solution: Analytics
title: 报告到变量映射
topic: 开发人员和实施
uuid: 4707660c-4be5-425c-a690-7bc6 df0 cc0 fa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 报告到变量映射

下表显示报表到变量的映射或报表或映射中使用的报表和变量。

**转换报表** 下表列出了用于填充每个报表的转化变量：

| 购买 |
|---|
| 转化和平均值 | s.events, s.products, s.purchaseID | 将 s.events 设置为购买、产品信息、订单号 |
| 收入 | s.events, s.products, s.purchaseID | 将 s.events 设置为购买、产品信息、订单号 |
| 订购 | s.events, s.products, s.purchaseID | 将 s.events 设置为购买、产品信息、订单号 |
| 件数 | s.events, s.products, s.purchaseID | 将 s.events 设置为购买、产品信息、订单号 |

| 购物车 |
|---|
| 转化和平均值 | s.events, s.products, s.purchaseID |  |
| 购物车 | s.events | 将 s.events 设置为 scOpen |
| 购物车查看 | s.events | 将 s.events 设置为 scView |
| 购物车加货 | s.events | 将 s.events 设置为 scAdd |
| 购物车减货 | s.events | 将 s.events 设置为 scRemove |
| 结账 | s.events | 将 s.events 设置为 scCheckout |

| 自定义事件 |
|---|
| 自定义事件 1 | s.events | 填充 event1 - event100 |
| … | … | 填充 event1 - event100 |
| 自定义事件 100 | s.events | 填充 event1 - event100 |

| 产品 |
|---|
| 转化和平均值 | s.events, s.products, s.purchaseID |  |
| 产品 | s.products, s.events | 根据右列量度的不同可能有所区别 |
| 交叉销售 | s.products, s.events, s.purchaseID | 根据右列量度的不同可能有所区别 |
| 类别 | s.products | 根据右列量度的不同可能有所区别 |

| 促销活动 |
|---|
| 转化和平均值 | s.products, s.events, s.campaign |  |
| 跟踪代码 | s.campaign |  |
| 创作元素 | 不适用 | Defined in [!DNL Analytics] |
| 促销活动 | 不适用 | Defined in [!DNL Analytics] |

| 客户忠诚度 |
|---|
| 客户忠诚度 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |

| 销售周期 |
|---|
| 首次购买间隔天数 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |
| 上次购买间隔天数 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |
| 访问量 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |
| 每日独特客户 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |
| 每月独特客户 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |
| 每年独特客户 | s.products, s.events, s.purchaseID | 在订单确认（“谢谢！”）页面中设置的变量 |

| 查找方法 |
|---|
| 反向链接域名 | 不适用 | 由 .JS 文件自动设置 |
| 原始反向链接域名 | 不适用 | 由 .JS 文件自动设置 |
| 搜索引擎 | 不适用 | 由 .JS 文件自动设置 |
| 搜索关键词 | 不适用 | 由 .JS 文件自动设置 |

| 访客资料 |
|---|
| 顶级域名 | 不适用 | 由 .JS 文件自动设置 |
| 语言 | 不适用 | 由 .JS 文件自动设置 |
| 时区 | 不适用 | 由 .JS 文件自动设置 |
| 州 | s.state | 在订单确认（谢谢！）页面中设置的变量 |
| 邮政编码 | s.zip | 在订单确认（谢谢！）页面中设置的变量 |
| 域名 | 不适用 | 由 .JS 文件自动设置 |

| 技术 |
|---|
| 浏览器 | 不适用 | 由 .JS 文件自动设置 |
| 操作系统 | 不适用 | 由 .JS 文件自动设置 |
| 显示器分辨率 | 不适用 | 由 .JS 文件自动设置 |

| 网站路径 |
|---|
| 页面值 | s.pageName, s.products, s.events, s.purchaseID |  |
| 登录页面 | s.pageName |  |
| 原始登录页面 | s.pageName |  |
| 每次访问页面 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 网站逗留时间 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 网站区域 | [!UICONTROL s.channel] | 与[!UICONTROL 流量]报表区域中的[!UICONTROL 渠道]报表相同 |

| 客户变量 |
|---|
| 自定义 eVar 1 | [!UICONTROL s.eVar] 1 |  |
| 自定义 eVar 2 | [!UICONTROL s.eVar] 2 |  |
| 自定义 eVar 3 | [!UICONTROL s.eVar] 3 |  |
| … |  |  |
| 自定义 eVar 75 | [!UICONTROL s.eVar] 75 |  |

## 流量报表 {#section_76A74C3D7B60461D9ADE0E5E183DD777}

下表列出用于填充每个报表的[!UICONTROL 流量]变量：

| 计算量度 |
|---|
| 不适用 | 不适用 | 不适用 |

| 网站流量 |
|---|
| 页面查看 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 每小时独特访客 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 每日独特访客 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 每月独特访客 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 每年独特访客 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 访问 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 文件下载 | 不适用 | 由 .JS 文件自动跟踪（具体取决于 .JS 变量设置） |

| 查找方法 |
|---|
| 反向链接域名 | 不适用 | 由 .JS 文件自动设置 |
| 反向链接 | 不适用 | 由 .JS 文件自动设置 |
| 搜索引擎 | 不适用 | 由 .JS 文件自动设置 |
| 搜索关键词 | 不适用 | 由 .JS 文件自动设置 |
| 回访频度 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 每日回访 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 回访 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 访问量 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |

| 访客资料 |
|---|
| 域名 | 不适用 | 由 .JS 文件自动设置 |
| 顶级域名 | 不适用 | 由 .JS 文件自动设置 |
| 语言 | 不适用 | 由 .JS 文件自动设置 |
| 时区 | 不适用 | 由 .JS 文件自动设置 |
| 访客详细信息 | 不适用 | 由 .JS 文件自动设置 |
| 最近 100 位访客 | 不适用 | 由 [!DNL Analytics] 中的业务规则计算 |
| 用户主页 | 不适用 | 由 .JS 文件自动设置 |
| 关键访客 | 不适用 | 基于访客 IP 地址 |
| 关键访客查看的页面 | 不适用 | 基于访客 IP 地址 |

| 地域划分 |
|---|
| 国家/地区 | 不适用 | 基于访客 IP 地址 |
| 美国各州 | 不适用 | 基于访客 IP 地址 |
| DMA | 不适用 | 基于访客 IP 地址 |
| 国际城市 | 不适用 | 基于访客 IP 地址 |
| 美国城市 | 不适用 | 基于访客 IP 地址 |

| 技术 |
|---|
| 浏览器类型 | 不适用 | 由 .JS 文件自动设置 |
| 浏览器 | 不适用 | 由 .JS 文件自动设置 |
| 移动设备 | 不适用 | 由 .JS 文件自动设置 |
| 浏览器宽度 | 不适用 | 由 .JS 文件自动设置 |
| 浏览器高度 | 不适用 | 由 .JS 文件自动设置 |
| 操作系统 | 不适用 | 由 .JS 文件自动设置 |
| 显示器颜色深度 | 不适用 | 由 .JS 文件自动设置 |
| 显示器分辨率 | 不适用 | 由 .JS 文件自动设置 |
| Netscape 插件 | 不适用 | 由 .JS 文件自动设置 |
| Java | 不适用 | 由 .JS 文件自动设置 |
| JavaScript | 不适用 | 由 .JS 文件自动设置 |
| JavaScript 版本 | 不适用 | 由 .JS 文件自动设置 |
| Cookie | 不适用 | 由 .JS 文件自动设置 |
| 连接类型 | 不适用 | 由 .JS 文件自动设置 |
| 区段 |

| 区段 |
|---|
| 最受欢迎页面 | s.pageName |  |
| 最受欢迎网站区域 | s.channel |  |
| 最受欢迎服务器 | s.server |  |

| 自定义分析 |
|---|
| 自定义链接 | s.linkName | 需要自定义实施 |
| 自定义分析 1 | s.prop1 |  |
| … | … |  |
| 自定义分析 75 | s.prop75 |  |

| 层次结构 |
|---|
| 层次结构 1 | s.hier1 |  |
| … | … |  |
| 层次结构 5 | s.hier5 |  |

## 路径分析报表 {#section_85E0A2396B894659A6BE572819263E95}

下表列出用于填充 [!DNL Analytics] 内各报表的路径变量：

| 页面 |
|---|
| 页面概要 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 页面值 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 最受欢迎页面 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 重新载入 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 页面点击次数 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 页面逗留时间 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 页面未找到 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |

| 登录和退出 |
|---|
| 登录页面 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 退出页面 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 退出链接 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |

| 完整路径 |
|---|
| 完整路径 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 最长路径 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 路径长度 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 每次访问逗留时间 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 单页访问量 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |

| 高级分析 |
|---|
| 上一页 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 下一页 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 上一页面流量 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 下一页面流量 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| PathFinder | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
| 流失 | s.pageName（或其他路径变量） | 此外还取决于内部业务规则 |
