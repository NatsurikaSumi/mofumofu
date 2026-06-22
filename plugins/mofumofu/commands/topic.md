---
description: 看某个 V2EX 主题的正文和回复,参数:主题ID(链接末尾数字)
allowed-tools: Bash(curl:*)
argument-hint: <主题ID>
---

# V2EX 主题 #$ARGUMENTS

主题正文:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?id=$ARGUMENTS"`

回复:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/replies/show.json?topic_id=$ARGUMENTS"`

## 你的任务

整理成易读中文(**不要原始 JSON**):

1. 顶部:标题、节点、作者、回复总数
2. 正文:用 content 字段(去掉多余空行,适当排版)
3. 回复:列楼层 `N楼 作者: 内容`,挑前 25 楼,超出则提示总楼数

若主题 ID 无效(返回空或错误),提示用户检查 ID(应为链接 url 末尾的纯数字)。
