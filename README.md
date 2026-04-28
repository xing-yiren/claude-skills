# Claude Skills

[[License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

A curated collection of reusable [Claude Code](https://claude.ai/code) skills. Each skill is a self-contained module that extends Claude's capabilities for specific content-generation and technical-writing workflows.

---

## 🧭 Philosophy

- **Evidence-driven** — every claim traces back to a source; no fabrication
- **Platform-aware** — skills adapt output to the target platform's conventions and constraints
- **Iteratively refined** — rules are hardened through real usage, not hypothetical scenarios
- **Mix & match** — each skill is independent; use what you need

---

## 📦 Skills

### `article-atomize`

> 将一篇长文拆解为多个单点短文，支持知乎和小红书双平台风格输出。

| 维度 | 说明 |
|------|------|
| **输入** | 一篇长文（Markdown / 文本 / 本地文件） |
| **输出** | 多篇可独立发布的短内容，按平台分目录存储 |
| **平台** | 知乎（正式技术口吻）+ 小红书（用户视角分享） |

**工作流：**
```
原文 → 证据台账 → 选题清单 → 平台化改写 → 文本检视 → 事实自检 → 成稿
```

**核心特性：**
- **证据台账** — 深度拆解原文：核心论点、支撑论据、关键数据、金句、不确定表述
- **关键词 & CTA 提取** — 识别产品/项目名、核心概念、平台资源 + 推广行动号召
- **双平台风格输出** — 标题规则、正文结构、文风约束、标签策略各平台独立配置
- **事实自检** — 发布前多维度校验（可追溯性、因果关系、限定词保留、平台声称验证）
- **宣传链接规则** — 发布/推广类内容自动补入项目地址和平台链接

📄 详细文档：[`skills/article-atomize/SKILL.md`](skills/article-atomize/SKILL.md)

---

### `technical-blog-generator-v2`

> 围绕指定技术主题自动搜索与抓取社区文章，可选结合源码分析，生成小红书技术博客。

| 维度 | 说明 |
|------|------|
| **输入** | 技术主题（关键词） |
| **输出** | 小红书格式技术推文（证据台账 + 草稿 + 原理图 + 自检报告） |
| **平台** | 小红书 |

**工作流：**
```
搜索 → 证据台账 → 源码验证（可选）→ 草稿生成 → 质量检视 → 事实自检 → 发布确认
```

**核心特性：**
- **结构化证据台账** — 从多篇文章中交叉验证，提取核心论点、支撑论据、关键数据
- **关键词 & CTA 提取** — 产品名、核心概念、平台资源自动归类
- **完整的小红书写作规范** — 标题 ≤20 字、反公式化 AI 句式、展示效果要求、标签策略
- **文本质量检视 + 事实自检** — 发布前双重校验
- **Mermaid 原理图模板** — 无配图时自动生成技术方案流程图
- **浏览器发布能力** — 确认后可一键发布至小红书（需处理登录态）

📄 详细文档：[`skills/technical-blog-generator-v2/SKILL.md`](skills/technical-blog-generator-v2/SKILL.md)

---

## 🚀 Getting Started

### Installation

Clone the repository and copy the desired skill to your project's `.claude/skills/` directory:

```bash
git clone https://github.com/xing-yiren/claude-skills.git
cp -r claude-skills/skills/article-atomize /your-project/.claude/skills/
```

Or use a single skill directly in your project by downloading just the SKILL.md file.

### Usage

Once installed, invoke a skill from within Claude Code:

```
/article-atomize 帮我拆这篇产品发布稿
```

Or let Claude auto-detect based on your task description.

---

## 📁 Repository Structure

```
claude-skills/
├── README.md                          ← This file
└── skills/
    ├── article-atomize/               ← Long-form → multi-platform short content
    │   └── SKILL.md
    └── technical-blog-generator-v2/   ← Tech topic → XHS blog post
        ├── SKILL.md
        └── templates/
            ├── diagram_mermaid_template.md
            └── xiaohongshu_post_template.md
```

---

## 📝 License

MIT — see [LICENSE](LICENSE) for details.

---

## 🔮 Roadmap

This repository will grow as more skills are developed and refined. Planned areas include:

- More platform support (WeChat Official Accounts, Bilibili, etc.)
- Content-type-specific variants (case studies, tutorials, comparison posts)
- Analysis & visualization skills (data storytelling, chart generation)
