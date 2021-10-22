---
description: 有关 Activity Map 中链接跟踪的常见问题解答。
title: 链接跟踪常见问题解答
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 2a20ce50f773c82856da59154bb212f1fca2b7ea
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 44%

---

# 链接跟踪常见问题解答

有关 Activity Map 中链接跟踪的常见问题解答。

>[!CAUTION]
>
>启用 Activity Map 跟踪后，**您可能会收集个人身份识别信息 (PII) 数据。**&#x200B;此类数据可用于（单独或与其他信息配合使用）识别、联系或查找个人，或者在上下文中识别个人。

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* 用户登录后可能出现在网站页眉/页脚的 `User ID` 链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。

## 何时进行链接跟踪？

Activity Map链接和区域标识在用户单击页面时发生。

## 默认情况下会跟踪哪些内容？

如果某个元素发生点击事件，该元素必须通过一些检查来确定AppMeasurement是否将其视为链接。 检查内容如下：

* 这是 `A` 或 `AREA` 标记 `href` 资产？
* 是否 `onclick` 属性 `s_objectID` 变量？
* 这是 `INPUT` 标记或 `SUBMIT` 值或子文本的按钮？
* 这是 `INPUT` 标记类型 `IMAGE` 和 `src` 资产？
* 这是 `BUTTON`?

如果以上任一问题的回答为是，则该元素将被视为链接，需要对其进行跟踪。

>[!IMPORTANT]
>
>AppMeasurement不会将具有属性type=&quot;button&quot;的Button标记视为链接。 请考虑删除按钮标记上的type=&quot;button&quot;，并改为添加role=&quot;button&quot;或submit=&quot;button&quot;。

>[!IMPORTANT]
>
>AppMeasurement会将具有以“#”开头的“href”的锚点标记视为内部目标位置，而不是链接（因为您没有离开页面）。 默认情况下，Activity Map 不跟踪这些内部目标位置，而是仅跟踪将用户导航到新页面的链接。

## Activity Map如何跟踪其他可视化HTML元素？

a.通过 `s.tl()` 函数。

如果点击是通过 `s.tl()` 调用时，Activity Map还会收到此点击事件，并确定 `linkName` 找到字符串变量。 期间 `s.tl()` 执行时，该linkName将设置为Activity Map链接ID。 发起 `s.tl()` 将使用调用来确定区域。 示例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b.通过 `s_objectID` 变量。 示例：

    &quot; 
    
    &lt;img onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot; src=&quot;someimageurl.png&quot; />
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot;>
    在此处链接文本
    &lt;/a>
    
    &quot;

>[!IMPORTANT]
>
>使用 `s_objectID` Activity Map。

## 能否提供一些将被跟踪的链接示例？

### 示例 1

```
  <a hef="/home?lang=en>Home</a>
```

### 示例 2

```
 <input type="submit" value="Submit"/>
```

### 示例 3

```
  <input type="image" src="submit-button.png"/>
```

### 示例4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### 示例5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## 能否提供一些不会被跟踪的链接示例？

1. 原因：锚标记不具备有效的 `href`:
   `<a name="innerAnchor">Section header</a>`

1. 原因：都不 `s_ObjectID` nor `s.tl()` 目前：

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 原因：都不 `s_ObjectID` nor `s.tl()` 目前：

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 原因：&quot;src&quot;属性缺少表单输入元素：

   `<input type="image"/>`

