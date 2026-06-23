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

## 说明

所有命令通过 `curl` 调 V2EX 公开 API v1,只读、不鉴权、不碰账号。返回数据由 Claude 整理成易读中文。

依赖:系统有 `curl`(macOS/Linux 自带)。
