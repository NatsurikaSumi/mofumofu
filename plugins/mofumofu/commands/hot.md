---
description: 刷 V2EX 当前热门主题(悠闲翻翻)
allowed-tools: Bash(curl:*)
---

# V2EX 热门主题

下面是 V2EX 当前热门主题的原始数据:

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/topics/hot.json"`

## 你的任务

把上面的 JSON 整理成清爽的中文列表给用户悠闲翻看,**不要输出原始 JSON**。每条:

```
序号. 标题
     节点 · 作者 · N 回复 · 链接
```

按回复数从高到低排序。标题保持中文原样。最后加一句轻松治愈的小提示,并告诉用户可以用 `/mofumofu:topic <主题ID>` 看某帖详情和回复(主题 ID = 链接 url 末尾的数字)。

若数据为空或返回报错(如限流),友好提示稍后再试。
