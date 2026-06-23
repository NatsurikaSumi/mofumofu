# mofumofu · もふもふ — V2EX 治愈系刷帖 Claude Code 插件

![Claude Code Plugin](https://img.shields.io/badge/Claude_Code-plugin-D97757)
![version](https://img.shields.io/badge/version-1.3.1-blue)
![license](https://img.shields.io/badge/license-MIT-green)
![V2EX](https://img.shields.io/badge/V2EX-public_API-2b2b2b)
![no token](https://img.shields.io/badge/token-not_required-success)

![demo](assets/demo.svg)

在 Claude Code 里悠闲撸一把 [V2EX](https://www.v2ex.com):热门、最新、按节点、看单帖与回复。もふもふ 一下,忙里偷个闲。

纯 V2EX 公开 API,**无需 token、任何人开箱即用、换电脑装上即用**。仅读不写,不碰你的账号。

## 安装

```
/plugin marketplace add NatsurikaSumi/mofumofu
/plugin install mofumofu@mofumofu
```

## 两种用法

**① 自然语言(skill 自动触发,不用记命令)** — 装好后直接说,Claude 自动调 V2EX:

> 「看看 V2EX 今天热门」 ·「搜一下 golang 的帖」 ·「把 1221901 那帖总结一下」 ·「来个下饭帖」 ·「看看 Livid 的主页」

**② Slash 命令(精确、可复用)** — 见下表。

## 命令

| 命令 | 作用 | 示例 |
|---|---|---|
| `/mofumofu:hot` | 当前热门主题 | `/mofumofu:hot` |
| `/mofumofu:latest` | 最新主题 | `/mofumofu:latest` |
| `/mofumofu:node <节点名>` | 某节点主题 | `/mofumofu:node jobs` |
| `/mofumofu:topic <主题ID>` | 单帖正文 + 回复 | `/mofumofu:topic 1221864` |
| `/mofumofu:search <关键词>` | 全站搜索(sov2ex 第三方搜索引擎) | `/mofumofu:search golang` |
| `/mofumofu:member <用户名>` | 用户主页(注册/简介/社交) | `/mofumofu:member Livid` |
| `/mofumofu:node-info <节点名>` | 节点详情(介绍/帖子数) | `/mofumofu:node-info go` |
| `/mofumofu:tldr <主题ID>` | **AI 总结长帖**(结论/争议/金楼,不用读几百楼) | `/mofumofu:tldr 1221864` |
| `/mofumofu:digest` | **AI 今日热门摘要**(30 秒看完今天在聊啥) | `/mofumofu:digest` |
| `/mofumofu:user-topics <用户名>` | 某人发过的主题 | `/mofumofu:user-topics Livid` |
| `/mofumofu:random` | 随机抽一帖摸鱼 | `/mofumofu:random` |
| `/mofumofu:reply-draft <主题ID>` | **AI 拟回复草稿**(只拟不发) | `/mofumofu:reply-draft 1221864` |
| `/mofumofu:fun` | 挑最下饭/治愈的帖 | `/mofumofu:fun` |
| `/mofumofu:member-card <用户名>` | 用户全貌(资料+发过的帖) | `/mofumofu:member-card Livid` |
| `/mofumofu:hot-image <主题ID>` | 抽帖里的图片链接 | `/mofumofu:hot-image 1221864` |

常用节点:`jobs` 酷工作 / `go` 程序员 / `create` 分享创造 / `qna` 问与答 / `hardware` 硬件 / `deals` 优惠信息。

## 效果预览

`/mofumofu:hot` 大致长这样(数据实时变化,下面是示例):

> 🐰 **V2EX 当前热门主题**
> 1. 突然想离婚了 — 生活 · 🔥 359 回复
> 2. 坐了朋友的电车,感觉小油车已是上时代产物 — 汽车 · 130 回复
> 3. 有没有特别想吃、吃到却大失所望的食物? — 问与答 · 128 回复
> ……
> 今日 V 站「离婚 / 油车焦虑 / 大 A 套牢」三连,人间真实 😌

几个 AI 增值命令:

- `/mofumofu:digest` 把热门归纳成几个话题簇,30 秒看完今天在聊啥
- `/mofumofu:tldr <主题ID>` 把几百楼回复浓缩成「结论 / 争议点 / 金楼」,不用一楼楼读
- `/mofumofu:fun` 专挑下饭好玩的帖,过滤水帖和酸学
- `/mofumofu:reply-draft <主题ID>` 帮你拟回复草稿(只拟不发,自己手动发)

## 原理

调用 V2EX 公开 API v1(`topics/hot`、`topics/latest`、`topics/show`、`replies/show`),免鉴权、只读。命令把返回的 JSON 交给 Claude 整理成易读中文列表。

## License

MIT
