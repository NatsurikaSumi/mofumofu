---
description: 从 V2EX 热门里随机抽一帖摸鱼
allowed-tools: Bash(curl:*)
---

# 🎲 随机摸鱼一帖

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/hot.json" | python3 -c "import sys,json,random;d=json.load(sys.stdin);t=random.choice(d);print(json.dumps({'title':t['title'],'node':t['node']['title'],'member':t['member']['username'],'replies':t['replies'],'content':(t.get('content') or '')[:600],'url':t['url'],'id':t['id']},ensure_ascii=False))"`

## 你的任务

上面是随机抽中的一个 V2EX 热门帖(JSON)。轻松随意地展示给用户(**不要原始 JSON**),像随手翻到一帖:

- 标题 + 节点 · 作者 · N 回复
- 正文摘要(content,太长适当截断)
- 链接
- 末尾提示:`/mofumofu:topic {id}` 看回复、`/mofumofu:random` 再抽一个

若返回为空/出错,友好提示稍后再试。
