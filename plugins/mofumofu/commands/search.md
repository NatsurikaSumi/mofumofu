---
description: 搜索 V2EX 全站帖子(sov2ex 第三方搜索引擎),参数:关键词
allowed-tools: Bash(curl:*)
argument-hint: <关键词>
---

# V2EX 搜索:$ARGUMENTS

!`curl -s -G --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.sov2ex.com/api/search" --data-urlencode "q=$ARGUMENTS" --data "size=15"`

## 你的任务

上面是 sov2ex(V2EX 第三方全站搜索引擎,V2EX 官方无搜索 API)返回的 JSON。整理成清爽中文列表(**不要原始 JSON**),每条:

```
序号. 标题 — 节点 · N 回复 · https://www.v2ex.com/t/{id}
```

字段在 `hits[]._source`(含 title / node / replies / id / content / created)。取前 15 条,按返回的相关度顺序。结尾标注总命中数(`total`)+ 提示用 `/mofumofu:topic <主题ID>` 看详情。

若 `total` 为 0 提示换个关键词;若请求失败(sov2ex 是第三方,可能限流或抽风)友好提示稍后再试。
