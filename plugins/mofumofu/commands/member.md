---
description: 看 V2EX 用户主页(注册时间/简介/社交),参数:用户名
allowed-tools: Bash(curl:*)
argument-hint: <用户名>
---

# V2EX 用户:$ARGUMENTS

!`curl -s --max-time 15 -A "Mozilla/5.0 (Macintosh)" "https://www.v2ex.com/api/members/show.json?username=$ARGUMENTS"`

## 你的任务

上面是 V2EX 用户信息 JSON。整理成中文展示(**不要原始 JSON**):

- **用户名** username(编号 id)
- **注册时间** created(Unix 秒,转成可读日期,如 2010-04-25)
- **签名/简介** tagline / bio(有才显示)
- **网站** website、**GitHub** github、**所在地** location、**公司** company、**职位** psn 等(逐项有才显示)
- 主页链接 https://www.v2ex.com/member/{username}

若用户不存在(返回错误或字段为空)提示检查用户名(区分大小写)。
