---
description: 刷 V2EX 最新主题
allowed-tools: Bash(curl:*)
---

# V2EX 最新主题

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/latest.json"`

## 你的任务

把上面的 JSON 整理成中文列表(**不要原始 JSON**),每条:

```
序号. 标题 — 节点 · 作者 · N 回复 · 链接
```

保持最新顺序(不要重排),挑前 20 条。结尾提示可以用 `/mofumofu:topic <主题ID>` 看详情。

若数据为空或返回报错,友好提示稍后再试。
