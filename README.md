# Paper Ops

学术写作、论文项目管理与七步修订技能包。

**v0.1.0 · MIT License**

项目仓库：[xy727682/paper-ops](https://github.com/xy727682/paper-ops)

[English](README.en.md) · [外部依赖](EXTERNAL_SKILLS.md) · [来源与署名](ATTRIBUTION.md) · [发行说明](RELEASE_NOTES.md)

## 包含什么

| 技能 | 负责什么 |
|---|---|
| [paper-ops](skills/paper-ops/SKILL.md) | 底稿与版本管理、实验数据来源、图表一致性、渲染与交付 |
| [academy-writing](skills/academy-writing/SKILL.md) | 团队自研的学术写作流程，涵盖文献语料、术语库、句式学习与证据一致性 |
| [seven-step-rebuttal](skills/seven-step-rebuttal/SKILL.md) | 团队自研的七步修订流程，串联批注、回复逻辑、作者手改和正文修改 |

三项技能可以独立使用，也可以配合使用。它们是供支持 SKILL.md 的智能体读取的工作流程，不是独立运行的论文生成软件。

`academy-writing` 随包提供；`ml-paper-humanizer` 为可选外部依赖，仅链接至 [Fwibo/ml-paper-humanizer](https://github.com/Fwibo/ml-paper-humanizer)，不分发其规则、脚本、语料或模型，不将外部作者列为本项目共同作者。

## 安装

先下载 [v0.1.0](https://github.com/xy727682/paper-ops/releases/tag/v0.1.0) 或克隆仓库：

```bash
git clone https://github.com/xy727682/paper-ops.git
```

将 `skills/paper-ops/`、`skills/academy-writing/`、`skills/seven-step-rebuttal/` 三个完整目录复制到所用智能体支持的技能目录。保留目录内部结构，不能只复制 SKILL.md。

- 安装目标目录已有同名技能时，先比较版本或另作备份，避免覆盖个人修改。
- 技能目录位置和加载方式以所用客户端说明为准；尚未做跨客户端兼容测试。
- 不需要安装外部技能即可使用本包的项目管理、学术写作与七步修订流程。
- 文档提取、LaTeX 编译和图像渲染使用宿主已有工具；本包不附带编译器、OCR 或文献全文。

## 使用示例

### 接入论文与新结果

```text
使用 paper-ops。底稿是 [main.tex 路径]，结果来自 [CSV 路径]。
只更新实验第二节及对应表格，保留其他章节。
生成独立工作副本，并列出本次改动和待填结果，不运行实验。
```

### 根据批注修订

```text
使用 seven-step-rebuttal。底稿是 [论文路径]，意见是 [批注 PDF 路径]。
逐条提取意见并对应正文，先列出困难问题的回应逻辑，再修改已明确的内容。
保留意见原话、作者手改和公式，输出 addressing 表与标记版。
```

### 局部修改

```text
只改 Table 1 的 caption，补一句下半部分仅供参考，不参与直接比较。
不要启动整稿审查或重写正文。
```

技能流程应服从这些明确范围。它不会把局部修改自动扩展为训练、付费请求、并行委派或对外发布。

## 能力边界

本包提供可执行的写作协作步骤和模板，不内置自动评分器，不声称能自行优化到最高分，也不附带论文全文库。academy-writing 指导为具体项目整理文献台账、术语库和句式库，所用文献由用户提供或在授权范围内获取。迭代围绕发现的具体问题展开，研究判断与最终稿由作者负责。

## 目录

```text
skills/
  paper-ops/
    SKILL.md
    references/                 文件、数据、图表与渲染四层指南
  academy-writing/
    SKILL.md
    references/                 文献语料、术语和表达精确性指南
  seven-step-rebuttal/
    SKILL.md
    templates.md                回复与意见映射空白模板
    round-playbook.md           完整修订轮次的组织方式
```

## Core contributors

- [dodn-2021](https://github.com/dodn-2021) — 共同开发者
- [xy727682](https://github.com/xy727682) — 共同开发者

## 许可

本发行包采用 [MIT License](LICENSE)。版权与开发者信息见 [ATTRIBUTION.md](ATTRIBUTION.md)。外部 ml-paper-humanizer 不随包分发，按其上游许可使用。
