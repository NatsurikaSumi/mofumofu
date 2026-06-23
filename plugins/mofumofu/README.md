# mofumofu · もふもふ

在 Claude Code 里悠闲撸一把 V2EX,忙里偷个闲。纯公开 API,无需 token。

## 命令

- `/mofumofu:hot` — 当前热门主题
- `/mofumofu:latest` — 最新主题
- `/mofumofu:node <节点名>` — 某节点主题(如 `jobs` / `go` / `create`)
- `/mofumofu:topic <主题ID>` — 单帖正文 + 回复(主题 ID = 帖子链接末尾数字)
- `/mofumofu:search <关键词>` — 全站搜索(走 sov2ex 第三方搜索引擎)
- `/mofumofu:member <用户名>` — 用户主页(注册时间/简介/网站/社交)
- `/mofumofu:node-info <节点名>` — 节点详情(介绍/帖子总数)
- `/mofumofu:tldr <主题ID>` — AI 把长帖几百楼回复总结成「结论/争议/金楼」
- `/mofumofu:digest` — AI 总结当前热门话题趋势(今日在聊什么)
- `/mofumofu:user-topics <用户名>` — 某人发过的主题列表
- `/mofumofu:random` — 从热门里随机抽一帖
- `/mofumofu:reply-draft <主题ID>` — AI 帮拟回复草稿(只拟不发,自己手动发)
- `/mofumofu:fun` — 从热门挑最有梗/下饭/治愈的帖
- `/mofumofu:member-card <用户名>` — 用户全貌卡片(资料 + 发过的帖)
- `/mofumofu:hot-image <主题ID>` — 抽帖正文里的图片链接

## 说明

所有命令通过 `curl` 调 V2EX 公开 API v1,只读、不鉴权、不碰账号。返回数据由 Claude 整理成易读中文。

依赖:系统有 `curl`(macOS/Linux 自带)。
