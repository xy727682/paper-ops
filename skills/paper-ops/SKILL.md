---
name: paper-ops
description: >-
  论文项目的现场运营层（文件/版本/底稿、实验数据台账与先写后填、图表视觉规范、渲染验收循环），用于论文底稿、实验结果、图表与交付管理；审稿修改可配合随包的 seven-step-rebuttal，学术写作配合随包 academy-writing，文风修订可选配外部技能。Triggers: 写论文, 改论文, 投稿, 压页, 底稿, 版本, 数据到了, 新数据, 补实验, 填数字, 占位, 重画图, 编译通过, 交付, 打包, overleaf, 交接, paper project, deadline.
---

# Paper Ops · 论文项目现场运营层

> 公开发行适配版。具体任务范围、工具权限及用户明确约定优先于以下默认流程。单句修改只做必要改动；不因本技能自动启动实验、付费调用、委派或公开发布。

## 随包能力与可选依赖

- `academy-writing` 与 `seven-step-rebuttal` 随发行包提供，分别用于学术写作及批注、审稿回复。
- `ml-paper-humanizer` 是可选外部依赖，不随包分发。只有已安装且适合任务时才使用；未安装时说明未使用外部技能，继续完成本技能可覆盖的工作，不自动下载或复制。
- 本技能本身不提供语料库、自动评分器或分数驱动的自动迭代。下面的审查循环用于发现和修复具体问题。

## 按任务规模使用

已明确底稿、数据和范围时直接继续，不重复索取确认。哈希、全页审查和打包用于有相应需求的整稿交付，不要求每次局部修改都执行。用户要求内部工作稿时保留明确占位及来源需求；最终提交版才要求清除占位。既有证据足够时不重做实验或工程验收。

句子怎么写归 academy-writing 和 ml-paper-humanizer，审稿回复工作流归 seven-step-rebuttal；本 skill 管它们都不管的：**改的是哪份文件、数字是哪个协议下测的、图读者实际看到什么、什么叫"做完了"**。

四层是地基→内容→呈现→总闸。每层详细规则在 references/ 下，按需读，不必全读。

## 项目工作流（按本次任务选用）

1. **锁底稿**：声明本轮底稿 = 路径 + 修改时间 + 哈希，写进工作日志。禁止用 mtime / 文件名 v 号推断"最新版"。多会话并行先查任务注册表。→ [references/layer1-files.md](references/layer1-files.md)
2. **查台账**：数据台账里有什么、状态是什么；新数据先入账再使用。数据没齐 → 走先写后填协议（占位写作）。→ [references/layer2-data.md](references/layer2-data.md)
3. **干活**：按任务路由（见下表）。动图遵守图表视觉规范。→ [references/layer3-figures.md](references/layer3-figures.md)
4. **验收**：编译通过 ≠ 完成。编译→渲染→逐页视觉审查→修复→再渲，连续两轮无新问题才算完。→ [references/layer4-acceptance.md](references/layer4-acceptance.md)
5. **交付**：快照（tar.gz+SHA256）→ 打包（zip 正斜杠、marked/clean 分开）→ 查目标文件锁 → 交付后自检。占位符清零闸：grep 占位符必须为 0。→ layer1 §交付 / layer2 §先写后填

## 路由表

| 任务 | 去哪里 |
|---|---|
| 起草/润色/翻译/术语/claim强度/数字指代 | academy-writing |
| 英文散文去 AI 味、section 写法、register | ml-paper-humanizer |
| 审稿意见回复、批注 inline 化、三件套、红底纹 | seven-step-rebuttal |
| 底稿/版本/快照/交接/打包 | 本 skill 第 1 层 |
| 数据到位、数字身份、基线漂移、先写后填 | 本 skill 第 2 层 |
| 图、表、caption、配色、字号 | 本 skill 第 3 层 |
| "做完了没有"、交付前检查 | 本 skill 第 4 层 |

## 红线速查（详细规则在 references）

- 底稿唯一且显式；产物进新目录，永不覆盖输入文件
- 正文每个数字能答五问：值、指标定义、协议(seeds/划分/预处理)、来源文件:单元格、数据版本
- 消融/变体行名字必须在正文有定义，无定义不背 claim
- 未标注的占位符不得进入最终提交版
- 图内简称 = 正文简称；caption 指标名/单位与图内逐字一致
- 重画图前列原图信息清单，重画后逐项核对；有现成图不自己重画
- 不动官方模板行距，不用负 \vspace 偷版面，图不飘到 Conclusion 后
- 视觉审查要自证（转录图中文字），不许"看起来没问题"
- 脚本只报异常，裁决在人；严禁为过脚本改坏对的文字

## 与既有 skill 的边界

- academy-writing 的"数字出处关"管"找得到表"，本 skill 第 2 层管"身份与到位节奏"；两者串联执行，先身份后出处
- seven-step-rebuttal 的"底稿唯一"是 rebuttal docx 场景；本 skill 第 1 层是全项目泛化，不冲突
- ml-paper-humanizer 只管英文句子层；图表与验收（第 3/4 层）不在其范围
