---
title: 反向链接类型
description: 推荐人类型，取决于访客的来源。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# 反向链接类型

“推荐人类型”维度报告哪些通用渠道访客点进来到您的站点。 Adobe维护每个维度项的规则，与营销 [渠道不同](marketing-channel.md)，组织维护每个渠道的规则。

## 用数据填充此维

此维引用Adobe内部的多个查找表。 每个值都基于点击 [的推荐人](referrer.md) ，这取决于 [内部URL过滤器](/help/admin/admin/internal-url-filter-admin.md)。 确保正确配置推荐人维和内部URL过滤器。

## 维项

维度项包括点击的推荐人类型。 具体值包括：

* **输入／标记书签**: 点击不存在推荐人数据。
* **搜索引擎**: 推荐人来自包括关键字查询字符串的可识别的搜索引擎。
* **社交网络**: 推荐人数据属于Adobe认可的社交网络。
* **其他网站**: 推荐人数据不属于Adobe识别的搜索引擎或社交网络。
* **硬盘**: 推荐人源于访客硬盘上网页的本地副本。
* **电子邮件**: 推荐人源于协议为或的 `imap://` URL `mail://`。 不包括在线电子邮件服务，因为这些服务通常使用 `https://` 协议。

### 社交网络

以下列表引用Adobe使用的“社交网络”查找表。 Adobe向Adobe列表客户提供此Analytics。 如果您希望建议Adobe向此列表添加域，请在您的组织中设置支持代表，与客户服务部门联系。

>[!NOTE]
>
>此列表不同于营销渠道处理规则中社交网 [络的默认列表](../c-marketing-channels/c-rules.md)。

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### “其他网站”维度项中的搜索引擎

在“视图类型”维中推荐人特定域时，可能会在“搜索引擎”下列出一些域，而在“其他网站”下列出。 例如，您可能会在“ `'google.com'` 其他网站”下看到。

* **“搜索引擎”维项中的搜索引擎域**: 该推荐人符合Adobe分类为搜索引擎的所有条件。 引用域是有效的搜索引擎， *引用* URL包含关键字查询字符串参数。
* **“其他网站”维项中的搜索引擎域**: 引用URL未满足要分类为搜索引擎的所有条件。 常见示例包括专用于搜索之外的其他功能的子域。 例如， `mail.google.com` 或 `autos.yahoo.com` 不是搜索引擎，但驻留在通常与搜索关联的顶级域上。 这些子域不包含关键字查询字符串，这就是它们包含在“其他网站”而不是“搜索引擎”下的原因。
