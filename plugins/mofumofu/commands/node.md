---
description: 刷 V2EX 某个节点的主题,参数:节点名(如 jobs/go/create/qna)
allowed-tools: Bash(curl:*)
argument-hint: <节点名,如 jobs>
---

# V2EX 节点:$ARGUMENTS

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?node_name=$ARGUMENTS"`

## 你的任务

把该节点的主题整理成中文列表(**不要原始 JSON**),每条:

```
序号. 标题 — 作者 · N 回复 · 链接
```

结尾提示几个常用节点(jobs 酷工作 / go 程序员 / create 分享创造 / qna 问与答 / hardware 硬件 / deals 优惠信息),以及用 `/mofumofu:topic <主题ID>` 看详情。

若节点不存在(返回空或错误),提示检查节点名(节点名是 v2ex.com/go/ 后面的英文短名)。
