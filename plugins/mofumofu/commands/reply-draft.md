---
description: AI 帮你拟 V2EX 回复草稿(只拟不发,参考后自己手动发),参数:主题ID
allowed-tools: Bash(curl:*)
argument-hint: <主题ID>
---

# 给 #$ARGUMENTS 拟回复草稿

主题:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?id=$ARGUMENTS"`

已有回复(看大家怎么说,避免重复):
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/replies/show.json?topic_id=$ARGUMENTS"`

## 你的任务

读懂帖子(title+content)和已有回复的氛围,帮用户拟 **2-3 条不同风格的中文回复草稿**(V2EX 风格、自然长度、别太长):

1. **真诚有用型** — 给信息、观点或建议
2. **轻松有梗型** — 玩梗/调侃,贴 V 站氛围
3. (可选)**一句话表态型** — 简短

每条标明风格;避免和已有回复重复观点。

⚠️ 末尾务必提醒:**这只是草稿,请你自己复制到 V2EX 手动发**——本插件只读不写、不会替你发帖。若主题 ID 无效提示检查。
