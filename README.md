[English](README.en.md) · 简体中文

# amber-goldenpotato

> ⚠️ **更正（2026-10-02，另一项）**：防御轴的一案 A-d511f9e8 在所有车道上改记 NA（考场判的不是考生交付的文件，判分还要求了题面没写的事）。分母不变，**过案数不变**，每条道的总分都带 `'`。本仓各期成绩表里这一格请按 NA 读，其余内容保留原样，以[更正声明](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02-a-d511f9e8.md)为准。

> **2026-10-07 更新**：A-24bcf707（运维）：判分器要求被指的移除提交在功能自身的文件上有删除行；题面问的是功能被移除或丢失的那个提交，并没有写这个要求。本车道（Qwen3.8-27B）只挂了这一项检查，所以这一格改记 NA（挂起），不记负。过案数不变（榜上 15'/24）；负案 8→7，NA 1→2；运维轴 5/6 不变、另有 1 个 NA。[W38 期文](results/2026-W38.md)里该格已照此改记。见[规范仓 2026-10-07 的更正](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-24bcf707.md)。

> **2026-10-07 更新（第二次）**：A-cdc3d11a（审查）：某个审查案上，判分器把一条格式正确的发现里的每个小点都当成一条未经证实的独立断言，又把答案清单之外的真实缺陷当成误报，所以一份正确、格式规范的审查报告也到不了及格线；该案在所有车道上挂起，分母不变，待判分器和考场修好、重新补考后再定。本车道（Qwen3.8-27B）这一格改记 NA（挂起），不记负；该案由负改记 NA 的车道共 27 条，没有重新考试。过案数不变（榜上 15'/24）；负案 7→6，NA 2→3；审查轴 0/2 不变、另有 1 个 NA。[W38 期文](results/2026-W38.md)里该格已照此改记。见[规范仓 2026-10-07 的更正（A-cdc3d11a）](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-cdc3d11a.md)。

用私有题库 **AMBER** 实测社区玩家 goldenpotato 自部署的 Qwen3.8-27B 推理端点，只公开结果，不公开题目。

## 成绩一览

<!-- scoreboard:start -->

![amber-goldenpotato 成绩一览：Qwen3.8-27B 逐轴过案数](results/assets/scoreboard.zh.png?v=20261009)

| 大类 | 轴 | 考什么 | Qwen3.8-27B · [W38](results/2026-W38.md) |
|---|---|---|:-:|
| 施工面 | 编码 | 照着需求把功能写对 | 5/6 |
|  | 交付 | 做完还得交得出东西 | 3/3 |
|  | 运维 | 照规程干脏活 | 5/6 · 1 NA |
|  | 需求 | 客户要 A 不要 B | 1/1 |
|  | 收敛 | 真干完，不绕圈装忙 | 1/1 |
| 判断面 | UI | 照设计稿做页面 | 0/1 |
|  | 视觉 | 给真截图挑毛病 | 0/1 |
|  | 防御 | 堵死校验器的漏网口 | 0/2 · 1 NA |
|  | 归因 | 毛病对到正确根因 | 0/1 |
|  | 审查 | 给别人的交付物挑错 | 0/2 · 1 NA |
|  | **合计** |  | **15'/24** |

每格 = 过了几案/该轴共几案（案 = 一道计分题）。NA = 这一案作废或暂停计分，不算过也不算没过；总分带 `'` 表示其中有 NA。多数轴只有 1–2 案，差一案读数就变，所以别把小差距当结论。各列考试周次相同（W38），具体日期可能不同，数字是当期快照。

<!-- scoreboard:end -->

## 这是什么

- 「道」= 同一个模型名在不同家的卖场/接口；「案」= 一道题，「卷」= 一场考试记录（一案多卷 = 一道题的几个变体场次）。

- 每期 `results/YYYY-Www.md`：同题、同 harness（跑考试并记分的程序），对目标模型跑全库（23 案 / 26 卷）。
- 一期固定报告：题集规模与哈希、每案得分与通过/失败、终端终态（程序跑完时的退出状态）、token 用量与时延、环境指纹、按证据纪律写的定性裁决。
- 题目、oracle（判分器）、transcript（答题全过程记录）、中间产物**永不公开**（见下「发布纪律」）。
- 姐妹仓：[amber-gpt](https://github.com/getaskclaw/amber-gpt)、[amber-crof](https://github.com/getaskclaw/amber-crof)、[amber-ollama](https://github.com/getaskclaw/amber-ollama)、[amber-devin](https://github.com/getaskclaw/amber-devin)、[amber-deepseek](https://github.com/getaskclaw/amber-deepseek)、[amber-commandcode](https://github.com/getaskclaw/amber-commandcode)、[amber-opencode](https://github.com/getaskclaw/amber-opencode)、[amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy)、[amber-kimi](https://github.com/getaskclaw/amber-kimi)、[amber-doubao](https://github.com/getaskclaw/amber-doubao)、[amber-stepfun](https://github.com/getaskclaw/amber-stepfun)。
- AMBER 是 agentic 实战题库（施工/运维/审查/视觉/需求漂移——题中要求中途变化），规范与制题工具见 [getaskclaw/amber](https://github.com/getaskclaw/amber)；考题本体私有。

## 渠道说明（本仓的特殊性）

本仓考的是**社区个人自部署端点**，不是厂商服务：一位 linux.do 网友（goldenpotato）用 3 张 V100 32G 跑 NVIDIA 官方 NVFP4 量化的 Qwen3.8-27B（魔改 vLLM TP3，KV cache FP8），限时开放给社区压测。

因此本仓成绩带三条额外口径：

1. **一次性快照**：端点限时开放（首发公告称约一天），关服后无法复测。本期成绩是考古标本，不是可持续追踪的车道。
2. **排队环境**：端点公共并发仅 3 路且与全论坛访客共享，考场为不给端点添堵采用单路串行。墙钟时间因此包含公共排队，跨仓比 wall 时须带此口径。
3. **量化实测样本**：W-NVFP4（部分层 FP8）+ KV-FP8 的激进量化在 agentic 实战题上的表现，本身就是本期的观测对象之一。

## 发布纪律（红线）

1. 只发：分数与聚合、token 用量、速度、定性裁决。
2. 永不发：题目内容、oracle/判分器、transcript、考生工作区、任何能复原题面的中间产物、端点访问凭证。
3. 每期必钉：模型 ID、effort 档（思考力度档位）、日期（UTC）、harness 版本、每案内容哈希（bundle_sha，每题内容的哈希指纹）。哈希用于对照 [amber](https://github.com/getaskclaw/amber) 的公开哈希清单，自证题集未变。
4. 案号与题目结构属私有面：公开结果里案例只用稳定别名（A-xxxxxxxx，哈希派生）+ bundle 哈希作句柄；内部案号、变体名、题目描述永不出现。
5. 基调：这是社区实测，不是对任何人的攻击。数据说话，措辞克制。

## 一个方法论前提

同一模型、同一端点，两次跑也可能不同分——推理参数、负载、服务端版本都在漂；个人自部署端点的负载漂移比厂商服务更大。所以这里的一切结论都带日期与档位。单日数字是快照，不是定律。

## 结果索引

| 期 | 内容 | 结论 |
|---|---|---|
| [2026-W38](results/2026-W38.md) | Qwen3.8-27B（NVFP4）@ 端点默认档 全库首考 | 案级 14/23；施工/文本/运维/漂移强（含 hard 区分器满分），审查/核验/视觉/前端 0 案过；effort 旋钮实证无效；wall 约为强车道 5-20 倍 |
| [2026-W38 更正特刊](results/2026-W38-correction.md) | W38 全库复核:本仓改判 0 格 · 挂起 3 格 | W38 首考 3 格挂起;若翻案 14/23 可能上移,定性段须同步复核 |

## 免责

与端点运营者、Qwen 团队、NVIDIA 无任何隶属/赞助关系。分数是特定日期、特定负载下的快照，不构成任何选型建议。
