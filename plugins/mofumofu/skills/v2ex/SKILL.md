---
name: v2ex
description: 浏览和搜索 V2EX(中文技术社区论坛)。当用户用自然语言提到 V2EX / V 站 / 刷帖 / 摸鱼看帖 / 今天 V 站在聊什么 / 搜 V2EX / 把某帖(某楼)总结一下 / 看某 V2EX 用户或节点 / 随便来个帖 时使用。调 V2EX 公开 API 拉取并整理成中文。只读、免 token、绝不替用户发帖。
---

# V2EX 浏览 / 搜索 skill

让用户用**自然语言**刷 V2EX(不用记 slash 命令)。纯 V2EX 公开 API v1,免 token、只读。
所有 curl 加 `-A "Mozilla/5.0 (Macintosh)"`;拿到 JSON 后**整理成清爽中文,不输出原始 JSON**。

## 意图 → 接口 映射

| 用户大概会说 | 接口 |
|---|---|
| 看 V2EX 热门 / 今天热的 | `curl ".../api/topics/hot.json"` |
| 最新帖 | `curl ".../api/topics/latest.json"` |
| 今天 V 站在聊啥 / 来份摘要 | `hot.json` → 归纳成几个话题簇(别逐条列) |
| 来个下饭 / 有梗 / 治愈的帖 | `hot.json` → 挑下饭的、过滤水帖和酸学 |
| 随便看一个 / 换一批 | `hot.json` → 随机挑(可用 `python3 -c "import json,random,sys;print(random.choice(json.load(sys.stdin))['id'])"`) |
| 搜 V2EX 关于 xxx | `curl -G ".../sov2ex.com/api/search" --data-urlencode "q=xxx" --data "size=15"`(第三方搜索,V2EX 官方无搜索 API) |
| 看某帖 / 帖子详情 | `topics/show.json?id=<ID>` + `replies/show.json?topic_id=<ID>` |
| 把某帖总结一下 / 几百楼太长 | 同上,但**浓缩**成 结论 / 争议点 / 金楼,别逐楼列 |
| 看某节点(jobs/go/create…) | `topics/show.json?node_name=<节点>` |
| 某节点详情(简介/帖子数) | `nodes/show.json?name=<节点>` |
| 看某用户资料 | `members/show.json?username=<用户名>` |
| 某人发过的帖 | `topics/show.json?username=<用户名>` |
| 某用户全貌 | `members/show` + `topics/show?username=` 合并 |
| 帮我拟个回复 | `topics/show?id=` + `replies/show?topic_id=` → 拟草稿(**只拟不发**) |
| 帖里的图 | `topics/show.json?id=<ID>` → 从 content 抽图片链接 |

base URL = `https://www.v2ex.com`。**主题 ID = 帖子链接末尾的数字**(如 v2ex.com/t/1221901 → 1221901)。

## 规则

- **只读不写**:绝不替用户发帖/回复;"拟回复"只产出草稿,提醒用户自己手动发。
- 整理输出用中文、清爽列表/卡片,链接可点;不要原始 JSON。
- 数据为空 / 请求失败(V2EX 或 sov2ex 偶尔抽风)→ 友好提示稍后再试。
- 每个意图都有对应的精确 slash 命令(`/mofumofu:hot` 等,见 `commands/`),自然语言走本 skill、想精确复用就用命令。
