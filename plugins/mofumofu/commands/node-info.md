---
description: 看 V2EX 节点详情(介绍/帖子数),参数:节点名
allowed-tools: Bash(curl:*)
argument-hint: <节点名>
---

# V2EX 节点详情:$ARGUMENTS

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/nodes/show.json?name=$ARGUMENTS"`

## 你的任务

上面是 V2EX 节点信息 JSON。整理成中文展示(**不要原始 JSON**):

- **节点** title(英文名 name)
- **帖子总数** topics
- **简介** header(节点描述)
- 节点链接 https://www.v2ex.com/go/{name}

结尾提示:用 `/mofumofu:node $ARGUMENTS` 看这个节点下的帖子列表。

若节点不存在(返回错误或空)提示检查节点名(节点名是 v2ex.com/go/ 后面的英文短名)。
