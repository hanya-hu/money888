# MONEY888

> A bilingual (Chinese-first) personal financial self-checkup tool for Chinese-American and overseas Chinese users investing in U.S. markets. Built as a Claude Skill. Education only — not investment advice.

> 一个中文优先的个人财务自检工具，服务在美华人和投资美国市场的海外华人。基于 Claude Skill 框架。仅作教育用途，非投资建议。

---

## 这是什么

MONEY888 是一个**访谈式个人财务自检工具**，结构化收集你的收入、资产、负债、税优账户、目标等信息，输出一份完整的诊断报告，包括净值快照、资产配置缺口、产品类别参考、专业服务转介清单和 90 天行动计划。

工具是**双轨制**的，开场会先问你属于哪一类：

**轨道 A：在美华人（28 题）**

适用：美国公民、绿卡、长期工作签证（H-1B / L-1 / O-1）持有者。

覆盖：401(k) / IRA / HSA / Roth 税优账户优先级、加州等高税州优化、集中持仓 unwind 策略、退休规划、估算 estate tax exposure（按 $15M citizen 豁免）。

**轨道 B：海外华人投资美国（25 题）**

适用：主要居住地不在美国，按 NRA（Non-Resident Alien）税务身份的华人。

覆盖：W-8BEN 优化、美中协定 10% 股息预扣、§871(d) 净基础租金申报、NRA estate tax $60K 阈值规避（vs 美国公民 $15M 豁免）、持有结构对比（个人 / LLC / Foreign Corporation / Foreign Trust）、Ireland-domiciled ETF 等价物（CSPX / VWRA）。

## ⚠️ 重要免责声明

**本工具不是投资建议、税务建议或法律建议**。所有输出仅作教育和自我整理用途。

工具创建者 / 维护者**不是注册的财务规划师 (CFP)、投资顾问 (RIA)、税务师 (CPA / EA) 或律师**。

理财涉及个人特殊情况和复杂规则，特别是跨境场景（错一步代价可能是数十万美元的额外税负）。任何具体决策必须咨询持牌专业人士。

完整免责声明请见 [DISCLAIMER.md](./DISCLAIMER.md)。

## 怎么用

### 方式一：在 Claude.ai 网页 / 桌面端使用

1. 下载本仓库的 [Releases](../../releases) 里最新的 `money888.skill` 文件（或自己用打包脚本生成）
2. 在 Claude.ai 设置里上传该 SKILL 文件
3. 跟 Claude 说"帮我做个财务自检"或"用 MONEY888 给我做个理财规划"

### 方式二：在 Claude Code 命令行使用

```bash
git clone https://github.com/hanya-hu/money888.git
cd money888
# 把整个目录拷贝到你的 Claude Code skills 目录
cp -r . ~/.claude/skills/money888/
```

然后在 Claude Code 里启用 Skill。

### 方式三：手动用作 Prompt

直接把 `SKILL.md` 和 `references/` 下的文件内容复制粘贴给任何能处理长上下文的 LLM（Claude / GPT-4 / Gemini）作为系统 prompt 使用。

具体安装步骤见 [INSTALL.md](./INSTALL.md)。

## 项目结构

```
money888/
├── README.md                              # 本文件
├── LICENSE                                # MIT License
├── DISCLAIMER.md                          # 完整免责声明
├── INSTALL.md                             # 安装和使用说明
├── CONTRIBUTING.md                        # 贡献指南
├── CHANGELOG.md                           # 版本变更记录
├── SKILL.md                               # SKILL 主调度文件
└── references/
    ├── question-bank.md                   # 轨道 A 问题库（28 题）
    ├── frameworks.md                      # 轨道 A 诊断和报告框架（7 节）
    ├── product-library.md                 # 轨道 A 产品参考库
    ├── overseas-question-bank.md          # 轨道 B 问题库（25 题）
    ├── overseas-frameworks.md             # 轨道 B 诊断和报告框架（9 节）
    └── overseas-product-library.md        # 轨道 B 产品参考库
```

## 设计原则

- **教育而非建议**：所有产品引用都附"公开理财教育常用代表，不是个人化推荐"的限定语
- **主动转介专业服务**：不只是说"建议你找专业人士"，而是写清楚找哪一类、怎么找（NAPFA / AICPA / ACTEC / SHIP 等可信渠道）、预期费用、第一次见面要问什么
- **双轨严格分流**：在美华人和海外华人的关注点完全不同，开场强制选路径，不混合两边内容
- **报告顺序硬性约束**：专业服务转介清单必须出现在 90 天自助行动清单**之前**，复杂决策必须先去开会再回来执行
- **数字写明出处和时点**：2026 年 IRS contribution limits、NRA $60K estate tax exemption、美中协定 10% 股息预扣等都注明法条来源（IRC §2102(b) 等），并提示"使用前向跨境 CPA 核实最新版本"

## 适用人群

✅ 适合：

- 在美华人想做一次系统的财务自检
- 海外华人投资美国市场，想搞清楚 NRA 税务和 estate tax 风险
- 准备移民美国的人，想提前做 step-up basis 规划
- 子女在美求学 / 工作的跨境家庭
- 想了解什么时候该找哪种专业人士、怎么找

❌ 不适合：

- 寻找具体股票买卖建议
- 替代注册财务规划师的工作
- 极度复杂的跨境场景（>$10M 资产 + 多国结构）—— 直接找跨境财富管理团队
- 完全没有耐心做 20-30 分钟访谈的人

## 关于 Claude Skills 框架

本工具基于 Anthropic Claude 的 Skills 框架构建。Skills 是一种结构化的能力扩展机制，让 Claude 在特定任务上加载专门的指令和参考材料。

了解更多：[Anthropic Skills Documentation](https://docs.claude.com/en/docs/agents-and-tools/agent-skills)

## License

[MIT License](./LICENSE)。允许商用、修改、再发布，但**必须保留原版完整的免责声明**（特别是关于"非投资建议"和"非专业人士"的部分）。

## 贡献

欢迎贡献。提交 PR 之前请先看 [CONTRIBUTING.md](./CONTRIBUTING.md)。

报告内容错误（特别是税务数字、法条引用过时）请直接提 Issue。

## Author

**Hanya** · [@realhanyahu](https://x.com/realhanyahu) on X

## 联系方式

所有沟通通过 [GitHub Issues](../../issues) 进行。

不接受个人财务咨询。如需个人化建议，请按工具输出指引找持牌专业人士。

---

**Last updated**: 2026 年 5 月
**Current version**: v1.0.0
**Tax data reference year**: 2026（每年 IRS 公告后需要更新）
