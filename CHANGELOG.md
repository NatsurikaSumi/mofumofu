# Changelog

本插件遵循语义化版本(SemVer)。

## v1.4.0
- 新增 `skills/v2ex` skill:支持**自然语言触发**——直接说「看 V2EX 热门」「把某帖总结一下」「来个下饭帖」即自动调,不用记 slash 命令
- 命令(精确)+ skill(自然语言)双模式并存
- README 加「两种用法」说明

## v1.3.1
- 补 MIT `LICENSE` 文件(plugin.json 已声明 MIT 但缺文件)
- `digest` 命令加错误兜底,15/15 命令失败/空结果都有友好提示
- README 加「效果预览」+ badges + 终端 demo 图
- GitHub repo 补 description + topics(可发现性)

## v1.3.0
- 新增 4 命令:
  - `reply-draft <主题ID>` — AI 拟回复草稿(只拟不发)
  - `fun` — 从热门挑最下饭/治愈的帖
  - `member-card <用户名>` — 用户全貌(资料 + 发过的帖)
  - `hot-image <主题ID>` — 抽帖正文里的图片链接

## v1.2.0
- 新增 4 命令:
  - `tldr <主题ID>` — AI 把几百楼回复浓缩成结论/争议/金楼
  - `digest` — AI 总结当前热门话题趋势(今日在聊什么)
  - `user-topics <用户名>` — 某人发过的主题
  - `random` — 从热门随机抽一帖

## v1.1.0
- 新增 3 命令:
  - `search <关键词>` — 全站搜索(走第三方 sov2ex,V2EX 官方无搜索 API)
  - `member <用户名>` — 用户资料(注册/简介/社交)
  - `node-info <节点名>` — 节点详情(介绍/帖子数)

## v1.0.0
- 首发,4 命令:`hot` / `latest` / `node <节点>` / `topic <主题ID>`
- 纯 V2EX 公开 API v1,无需 token,任何人开箱即用
