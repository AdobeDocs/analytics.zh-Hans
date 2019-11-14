---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# visitorID

可根据 变量或 IP 地址/用户代理确认访客。

<!-- 

visitorID.xml

 -->

*`visitorID`* 最长可包含 100 个字母数字字符，且不得包含连字符。

如果您显式设置了一个自定义 ID，那么在出现其他 ID 方法之前将始终使用此 ID。

使用顺序如下：s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA。

| ** 最大大小** | ** 调试程序参数** | ** 填充报表** | ** 默认值** |
|---|---|---|---|
| 100 字节 | vid | 不适用 | "" |

**语法和可能值** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE]*`visitorID`* 变量不应包含连字符。

**示例** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**配置设置** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

无
