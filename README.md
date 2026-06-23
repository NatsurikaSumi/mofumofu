# mofumofu · もふもふ — V2EX 治愈系刷帖 Claude Code 插件

在 Claude Code 里悠闲撸一把 [V2EX](https://www.v2ex.com):热门、最新、按节点、看单帖与回复。もふもふ 一下,忙里偷个闲。

纯 V2EX 公开 API,**无需 token、任何人开箱即用、换电脑装上即用**。仅读不写,不碰你的账号。

## 安装

```
/plugin marketplace add NatsurikaSumi/mofumofu
/plugin install mofumofu@mofumofu
```

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

## 原理

调用 V2EX 公开 API v1(`topics/hot`、`topics/latest`、`topics/show`、`replies/show`),免鉴权、只读。命令把返回的 JSON 交给 Claude 整理成易读中文列表。

## License

MIT
