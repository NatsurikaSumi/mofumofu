---
description: 看某 V2EX 用户发过的主题,参数:用户名
allowed-tools: Bash(curl:*)
argument-hint: <用户名>
---

# $ARGUMENTS 发过的主题

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?username=$ARGUMENTS"`

## 你的任务

上面是该用户发过的主题 JSON。整理成中文列表(**不要原始 JSON**),每条:

```
序号. 标题 — 节点 · N 回复 · 链接
```

按发帖时间(created)新 → 旧。结尾提示用 `/mofumofu:member $ARGUMENTS` 看 ta 的资料、`/mofumofu:topic <主题ID>` 看某帖。

若该用户没发过主题或不存在(返回空/错误),友好提示检查用户名(区分大小写)。
