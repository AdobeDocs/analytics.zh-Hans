---
title: 日志文件
description: 获取日志文件以进行故障排除。
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---


# 日志文件

>[!IMPORTANT]
>
>Adobe将于2021年3月1日将Ad Hoc Analysis改为停产。 [了解更多...](https://adobe.ly/discoverworkspace).

对Ad Hoc Analysis的问题进行故障诊断时，有时需要获取其日志文件。 Adobe可以使用日志文件查找问题的根本原因并提供解决方案。 该文 `discover.log` 件包含所有会话中的所有用户交互、报告加载信息和Java错误消息。 它会散列任何受保护的信息，如用户的口令。 大日志文件以10 MB的增量进行拆分。 为日志文件提供Adobe时，请确保选择所有文件。

## Windows

获取 `discover.log` Windows文件：

1. 单击开始菜单并选 **择**“运行”，或 `[Win]` 按+ `[R]`。
2. 将以下内容粘贴到文本字段中，然后单击“确 **定”**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. 高亮显示文件夹中的所有文件，然后右键单击并选 **择“发送到”>“压缩（压缩）文件夹”**。
4. 为Adobe代表提供。zip文件。

## Mac

要获取Mac `discover.log` OS的文件，请执行以下操作：

1. 打开Finder并导航到 `/Users/your-user/.adobe/Discover/log`
2. 高亮显示文件夹中的所有文件，然后右键单击并选择“压 **缩”**。
3. 为Adobe代表提供。zip文件。

如果压缩文件的总大小超过10 MB,Adobe代表可以提供临时FTP位置。
