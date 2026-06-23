---
description: 抽出某 V2EX 帖正文里的图片链接,参数:主题ID
allowed-tools: Bash(curl:*)
argument-hint: <主题ID>
---

# 🖼️ #$ARGUMENTS 的图片

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/show.json?id=$ARGUMENTS"`

## 你的任务

从帖子的 `content` / `content_rendered` 字段里**抽出所有图片链接**(markdown 的 `![](url)`、HTML 的 `<img src>`、或裸图片 URL;常见图床 imgur / i.v2ex.co / sm.ms / 等):

- 标注帖子标题
- 逐行列出每个图片 URL(方便直接点开看)
- 若帖子正文里没有图片,直接说"这帖没图 🐰"

末尾提示 `/mofumofu:topic $ARGUMENTS` 看帖子全文 + 回复。若主题 ID 无效提示检查。
