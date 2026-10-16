# clarify-first · 理解思考询问

一条给 AI 助手用的**对话协议**：凡「要调研」或「要动手」的请求，先**极简判读**，再提出**还需要确认的问题**，得到答复后才给**方案**，方案获确认后才**执行**。

> 把「确认」从 *方案* 提前到 *理解*。

## 四拍

| 拍 | 做什么 | 约束 |
|---|---|---|
| ① 判读 | 问题是什么、大体怎么解 | 最多 1–2 次轻量探查；不许写成半个方案 |
| ② 问 | `我理解的是：…` + `要问你：1. …` | 只问还定不下来的；一次问完；≤4 条 |
| ③ 方案 | 做什么 / 为什么（附证据）/ 影响与代价 / 怎么回滚 / 等确认 | 用户答完才给 |
| ④ 执行 | 用户确认或修改后才动手 | 以用户最后那版为准 |

## 豁免（直接答 / 直接做）

1. 纯事实查询（「这文件在哪」「这包多大」）
2. 用户明说「直接做」「别问了」
3. 同一任务的后续步骤（上一轮已问清）

## 安装

DSH 会监听技能根目录，放进去即生效，无需重启：

```powershell
# 项目级
git clone https://github.com/fengzhizhi55/clarify-first.git "你的项目/.dsh/skills/clarify-first"

# 用户级（所有工作区可用）
git clone https://github.com/fengzhizhi55/clarify-first.git "$env:USERPROFILE\.dsh\skills\clarify-first"
```

也可以直接把仓库里的 `SKILL.md` 拷成 `<技能根>/clarify-first/SKILL.md`。

> 注意：DSH 的技能名必须匹配 `^[a-z0-9]+(?:-[a-z0-9]+)*$`（小写 ASCII 短横线），中文名会被直接忽略。

## 可调项

- 探查预算：默认 1–2 次；想更省就改成 0 次
- `我理解的是` 那一行：嫌啰嗦可去掉，只留「要问你」
- 豁免清单：按实际需要增删

## English

**clarify-first** is a conversation-protocol skill for AI coding agents. For any request that needs research or action, the agent must: (1) take a *minimal* read of the problem (no deep investigation up front), (2) ask only the questions that still need answering, (3) propose a full plan once answered, and (4) act only after the plan is approved. Trivially factual questions and explicit "just do it" instructions are exempt.

## License

MIT © 2026 fengzhizhi55
