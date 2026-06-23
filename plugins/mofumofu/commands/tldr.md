---
description: AI 浓缩某 V2EX 帖子的回复(结论/争议/金楼),不用读几百楼。参数:主题ID
allowed-tools: Bash(curl:*)
argument-hint: <主题ID>
---

# V2EX TL;DR #$ARGUMENTS

主题:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?id=$ARGUMENTS"`

回复:
!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/replies/show.json?topic_id=$ARGUMENTS"`

## 你的任务

**不要逐楼列出**。把这个帖子和它的全部回复**浓缩**成中文 TL;DR:

1. **一句话主题**:楼主在问/说什么(看 title + content)
2. **结论/共识**:回复里的主流观点、被多数人赞同的结论(2-4 点)
3. **争议点**:有没有吵起来、对立的观点(若有)
4. **金楼**:最有信息量或最有梗的 1-2 条回复(注明楼层/作者)
5. 末尾一句总评 + 总楼数

目标:让用户不用读几百楼就知道这帖在聊什么、结论是什么。若主题 ID 无效(返回空/错误)提示检查 ID。
