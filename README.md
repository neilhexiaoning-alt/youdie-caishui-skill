# youdie-caishui-skill

> 友蝶财税业务专用 Agent Skill —— 品牌知识库、服务口径、文案规范一键调用。
> 兼容 **OpenClaw**、**WorkBuddy**、**悟空** 以及 Claude Code / Cowork 等主流 AI Agent 平台。

[![Skill Version](https://img.shields.io/badge/skill-v1.0.0-gold)](./SKILL.md)
[![License](https://img.shields.io/badge/license-MIT-blue)](./LICENSE)
[![Language](https://img.shields.io/badge/language-中文-red)](./README.md)
[![Compatible](https://img.shields.io/badge/compatible-OpenClaw%20%7C%20WorkBuddy%20%7C%20悟空-brightgreen)](#安装与使用)

## 项目简介

这是一个为**昆明友蝶财务咨询服务有限公司**（以及大理友蝶财税服务有限公司）打造的 **Agent Skill**。它把友蝶财税的品牌信息、服务体系、资质荣誉、文案规范等内容沉淀成结构化的知识库。

本 skill 基于通用的 **Markdown + frontmatter** 开放格式，可以被 **OpenClaw、WorkBuddy、悟空** 以及 Claude Code、Cowork、Claude.ai Projects 等任何支持 Agent Skill 规范的平台直接加载和调用，让各类 AI 助手在处理友蝶相关任务时能够：

- ✅ 保持**品牌口径一致**——使命、愿景、承诺、服务名称不跑偏
- ✅ 遵守**合规底线**——不做超能力承诺、不违反广告法
- ✅ 适配**多种场景**——从朋友圈短文案到商务提案全覆盖
- ✅ 复用**标准模板**——介绍 PPT、合作提案、客户问答开箱即用
- ✅ 跨**多 Agent 平台**——一处维护，多处调用

## 适用场景

| 场景 | 说明 |
|------|------|
| 📢 **营销宣传** | 朋友圈、公众号、小红书、抖音脚本、海报文案 |
| 💼 **商务文档** | 合作提案、服务方案、战略合作意向书、申报材料 |
| 🎯 **客户服务** | 客户咨询应答、疑难问题解释、报价逻辑说明 |
| 📚 **内部培训** | 新员工入职、合伙人培训、公开讲座稿件 |
| 🏆 **资质申报** | 协会 / 政府 / 示范单位申报材料 |

## 项目结构

```
youdie-caishui-skill/
├── SKILL.md                          # 技能主入口（AI 助手首先读这个）
├── README.md                         # 本文件（GitHub 展示用）
├── LICENSE                           # MIT 开源协议
├── references/                       # 详细知识库（按需加载）
│   ├── company-profile.md            # 公司完整档案
│   ├── services.md                   # 24 项服务详解
│   ├── credentials.md                # 资质荣誉清单
│   ├── brand-voice.md                # 品牌调性与文案规范
│   └── faq.md                        # 客户常见问答
└── assets/                           # 可复用模板
    ├── intro-deck-outline.md         # 介绍 PPT 结构骨架
    ├── wechat-post-templates.md      # 朋友圈文案模板（17 个）
    └── proposal-outline.md           # 合作提案骨架
```

## 安装与使用

> **通用步骤**：所有平台第一步都是把本仓库下载到本地。
>
> ```bash
> git clone https://github.com/neilhexiaoning-alt/youdie-caishui-skill.git
> ```

### 🐉 OpenClaw

OpenClaw 支持标准 Agent Skill 格式，把整个 `youdie-caishui-skill/` 目录放到 OpenClaw 的 skills 加载路径（通常是 `~/.openclaw/skills/` 或工作区内的 `.openclaw/skills/`），重启即可。触发方式：

- 在对话中提及"友蝶""友蝶财税""kmudee"等关键词
- 或使用 `/skill youdie-caishui` 显式加载

### 🤝 WorkBuddy

在 WorkBuddy 的**技能界面**直接安装，两种方式任选其一：

1. **本地上传**：下载本仓库的 [`youdie-caishui-skill.zip`](./youdie-caishui-skill.zip)，在技能界面点 **上传 zip** 即可
2. **仓库导入**：在技能界面选"从 GitHub 导入"，粘贴本仓库地址 `https://github.com/neilhexiaoning-alt/youdie-caishui-skill`

安装完成后，在对话中提到"友蝶"等关键词自动触发。

### 🐵 悟空

在悟空的**技能界面**直接安装，两种方式任选其一：

1. **本地上传**：下载本仓库的 [`youdie-caishui-skill.zip`](./youdie-caishui-skill.zip)，在技能界面点 **上传 zip** 即可
2. **仓库导入**：在技能界面选"从 GitHub 导入"，粘贴本仓库地址 `https://github.com/neilhexiaoning-alt/youdie-caishui-skill`

安装完成后，在对话中提到"友蝶"等关键词自动触发。

### 🤖 Claude Code / Cowork

1. 把整个目录放到 Claude 的 skills 路径下（`~/.claude/skills/` 或项目级的 `.claude/skills/`）
2. 在对话中触发，Claude 会自动加载 `SKILL.md` 和相关 reference

### 💬 Claude.ai 网页版 / Projects

1. 打开 `SKILL.md`，复制全部内容作为 Project 的 System Instructions
2. 把 `references/` 和 `assets/` 下的 Markdown 文件作为 Project Knowledge 上传
3. 对话时直接描述任务，Claude 自动按 skill 规则产出

### 📦 打包为 .skill 文件

使用 skill-creator 工具打包，方便分发：

```bash
python -m scripts.package_skill youdie-caishui-skill/
```

### 📋 平台对照表

| 平台 | 接入方式 | 操作难度 | 备注 |
|------|---------|:---:|------|
| **OpenClaw** | skills 目录放置 | ⭐ | 原生 Agent Skill 支持 |
| **WorkBuddy** | 技能界面 · 上传 zip 或 GitHub 导入 | ⭐ | 图形化一键安装 |
| **悟空** | 技能界面 · 上传 zip 或 GitHub 导入 | ⭐ | 图形化一键安装 |
| Claude Code / Cowork | skills 目录放置 | ⭐ | 官方标准方式 |
| Claude.ai Projects | System Instructions + Knowledge | ⭐⭐ | 需手动粘贴 |

## 使用示例

> 下列示例适用于所有支持的平台（OpenClaw / WorkBuddy / 悟空 / Claude 等），以下统称"AI 助手"。

### 示例 1：生成朋友圈文案

**你问 AI 助手**：
> 帮我写一条朋友圈文案，主题是年底汇算清缴。

**AI 助手会**：
1. 读取 `SKILL.md` 了解上下文
2. 加载 `brand-voice.md` 掌握文案调性
3. 参考 `wechat-post-templates.md` 的"汇算清缴季"模板
4. 产出一条 6 行以内、符合友蝶调性、不违规的朋友圈

### 示例 2：回答客户咨询

**客户问**：
> 你们代账一个月多少钱？

**AI 助手会**：
1. 读取 `faq.md` 中的 Q5 标准回复
2. 根据 `brand-voice.md` 用"先共情、后引导"的话术
3. 给出不直接报价、引导加微信细聊的回复

### 示例 3：起草合作提案

**你说**：
> 帮我给昆明某商会写一份会员增值服务合作提案。

**AI 助手会**：
1. 读取 `proposal-outline.md` 的"针对商会 / 协会"章节
2. 调用 `company-profile.md` + `credentials.md` 填充资质背书
3. 用 `services.md` 的规范服务名称列出增值内容
4. 按标准结构输出提案初稿

## 核心原则（AI 助手在使用此 skill 时会自动遵守）

### ✅ 必须做到
- 使用**规范品牌名**（友蝶财税、昆明友蝶财务咨询服务有限公司）
- 服务名称用 **`services.md` 中的标准命名**（不自创）
- 引用**完整资质名称**（不简化成"AAA 级认证"这种模糊说法）
- 核心承诺**逐字引用**："凡是友蝶财务导致的税务罚款，我们全额承担"

### ❌ 禁止做
- 编造**具体报价**（代账月费、咨询费等）
- 承诺**节税比例**（如"保证节税 30%"）
- 使用**极限用语**（绝对、唯一、最、100%）
- 虚构**客户案例**（真实公司名、具体金额）
- 贬低**同行**或暗示违规操作

## 内容来源

本 skill 的内容基于以下官方资料：

- 友蝶财税企业介绍 PPT（2024 版）
- 官网 [www.kmudee.com](https://www.kmudee.com)
- 云南省代理记账行业协会、昆明市商务代理协会授牌文件
- AAA 级诚信经营示范单位认证材料
- 云南省数字化财税服务示范单位认证材料
- 办公室资质展示墙的资质牌匾照片

## 维护与更新

### 谁可以修改本 skill？
- 友蝶财税运营负责人 / 指定内容管理员
- 品牌核心表述（使命、愿景、承诺）变更需经老板确认

### 更新流程
1. Fork 本仓库或在 `main` 分支创建新分支
2. 修改相应的 `references/` 或 `assets/` 文件
3. 在本 README 的"变更日志"中记录
4. 提 PR 或直接合并（视团队流程而定）

## 变更日志

### v1.1.0（2026-04-24）
- 🔌 新增对 **OpenClaw、WorkBuddy、悟空** 三个 Agent 平台的接入说明
- 📋 新增平台对照表，明确各平台的加载方式与能力差异
- 📝 使用示例与核心原则改为"AI 助手"通用表述

### v1.0.0（2026-04-24）
- 🎉 初始版本发布
- 包含完整的品牌档案、24 项服务清单、资质荣誉、品牌调性、FAQ
- 提供介绍 PPT、朋友圈文案、合作提案三大模板

## 开源协议

本项目使用 [MIT License](./LICENSE)。

> ⚠️ **注意**：MIT 协议允许代码和文档结构的复用，但本 skill 中涉及的**友蝶财税品牌信息、商标、业务资质**为昆明友蝶财务咨询服务有限公司专有。其他公司 / 个人请勿直接套用本 skill 的品牌内容来推广自己的业务。

## 联系方式

- **公司**：昆明友蝶财务咨询服务有限公司
- **官网**：[www.kmudee.com](https://www.kmudee.com)
- **商务合作**：通过官网联系我们

## 关于 Agent Skill

Agent Skill 是一种通用的 AI Agent 能力扩展机制——通过 `SKILL.md`（主入口，含 frontmatter 元数据）+ `references/` 知识库 + `assets/` 模板，让 AI 助手在特定领域内按"领域专家"的方式工作。

该格式最初由 Anthropic 在 Claude Skill 中提出，现已被 **OpenClaw、WorkBuddy、悟空** 等国内主流 Agent 平台采用或兼容。

相关资源：
- [Anthropic Claude 官方文档](https://docs.claude.com)
- [Claude Code](https://claude.com/claude-code)

---

**Made with 💛 by 友蝶财税 · 适配多 Agent 平台**
