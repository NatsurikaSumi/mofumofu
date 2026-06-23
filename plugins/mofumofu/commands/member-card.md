---
description: V2EX 用户全貌卡片(资料 + 发过的帖),参数:用户名
allowed-tools: Bash(curl:*)
argument-hint: <用户名>
---

# 👤 V2EX 用户卡片:$ARGUMENTS

资料:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/members/show.json?username=$ARGUMENTS"`

发过的主题:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?username=$ARGUMENTS"`

## 你的任务

把这个用户整理成一张中文「用户卡片」(**不要原始 JSON**):

**📇 资料**(来自第一段):
- 用户名(编号 id) · 注册时间(created 是 Unix 秒,转可读日期)
- 签名/简介(tagline / bio)
- 网站 / GitHub / 所在地 / 公司 等(逐项有才列)

**📝 最近发的主题**(来自第二段,列表):
`序号. 标题 — 节点 · N 回复 · 链接`(按时间新→旧,最多 10 条)

末尾提示 `/mofumofu:topic <主题ID>` 看 ta 某帖详情。若用户不存在(返回错误/空)友好提示检查用户名。
