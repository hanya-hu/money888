# Changelog

本项目变更记录，遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/) 格式。

## [1.0.0] - 2026-05

### 首发版本

**双轨制 SKILL 架构**：

- 第零阶段路径分流（在美华人 / 海外华人）
- 轨道 A：在美华人 28 题访谈 + 7 节诊断报告
- 轨道 B：海外华人投资美国 25 题访谈 + 9 节诊断报告

**轨道 A 内容**：

- 28 道结构化问题，覆盖收入、支出、资产、负债、保险、目标
- 净值快照 + 现金流诊断 + 三红旗机制
- 2026 年税优账户优先级瀑布（401(k) $24,500 / IRA $7,500 / HSA $4,400/$8,750）
- 含 SECURE 2.0 catch-up Roth 强制规则（FICA >$150K 触发）
- 资产配置诊断（110 - age 起点，按风险承受度调整）
- 产品类别参考库（VTI / VXUS / BND 等代表性 ETF）
- HNW 集中持仓处理工具：Exchange Fund (Section 351)、Direct Indexing、CRT、DAF、CLT、Section 1042、OZ
- 慈善 + 遗产规划工具（ILIT、SLAT、GRAT、QPRT、FLP、Dynasty Trust）概念性介绍
- 专业服务转介地图（11 项触发条件，6 类专业人士详解）
- 90 天自助行动清单
- 完整免责声明

**轨道 B 内容**：

- 25 道结构化问题，覆盖国籍、居住地、美国资产、本国资产、跨境家庭、移民意向、合规
- 身份税务画像（NRA / 持绿卡 / SPT 触发判定）
- 适用所得税协定状态（美中 10% 股息）
- estate tax 协定状态（美中**没有** estate treaty）
- US-Situs 资产清单（每项标注 estate tax 触发器）
- estate tax exposure 估算（基于 NRA $60K 豁免）
- 合规账户和资金路径（IBKR / Schwab International / Firstrade 对比）
- W-8BEN 优化指南
- §871(d) 净基础租金申报选举说明
- 持有结构对比（个人 / LLC / Foreign Corp / Foreign Trust / 寿险包裹）
- 产品类别参考库（按 estate tax 风险分级；含 Ireland-domiciled 等价物 CSPX / VWRA）
- 跨境专业服务转介（estate attorney / 国际税务 CPA / 移民律师）

**安全护栏**：

- 所有产品引用强制带"公开教育常用代表，非个人化推荐"限定语
- 报告输出顺序硬性约束：专业服务转介清单必须在 90 天自助清单之前
- 90 天自助清单只放用户自己能直接执行的事
- 对个股、加密货币标的、whole life / 可变年金、PFIC 边界场景一律转介专业人士
- 海外华人路径专属"警觉但不恐吓"语气护栏

**安装支持**：

- 三种使用方式：Claude.ai 上传 .skill / Claude Code 命令行 / 手动 prompt
- 完整的 INSTALL.md 操作指南

### 关键税务数字（2026 年版）

工具内嵌的 2026 年关键数字：

- 401(k) elective deferral：$24,500
- 401(k) catch-up (50+)：$8,000
- 401(k) super catch-up (60-63)：$11,250
- IRA：$7,500
- IRA catch-up (50+)：$1,100
- HSA self-only：$4,400
- HSA family：$8,750
- HSA catch-up (55+)：$1,000
- Roth IRA phase-out 单身：$153,000-$168,000
- Roth IRA phase-out 夫妻合报：$242,000-$252,000
- US citizen / 绿卡 estate tax 豁免：$15,000,000
- NRA estate tax 豁免：$60,000
- 默认 NRA 股息预扣率：30%
- 美中协定股息预扣率：10%
- 2026 年 NRA 给非美籍配偶赠与豁免：约 $190,000
- FIRPTA 卖出预扣：15%

**重要提醒**：每年 IRS 公告新数字后需要更新。下一次更新预计在 2026 年 11 月 IRS 发布 2027 年 limits 之后。

---

## 未来路线图（非承诺）

可能的方向，欢迎 PR：

- **轨道 C**：英国 / 欧盟华人投资美国（适用 estate tax treaty 不同规则）
- **轨道 D**：澳洲 / 新西兰华人路径
- 英文版 README 和 SKILL（`SKILL.en.md`、`question-bank.en.md` 等）
- 更细分的场景包：仅美国房产投资专项、仅子女教育资金专项、仅退休规划专项
- 简化版 quick mode（10 题快速版）
- 集成 Claude API 自动化打包发布到 Releases

---

## 版本号约定

遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)：

- **MAJOR**：访谈结构或报告框架重大变更（比如新增轨道、删除大段问题）
- **MINOR**：新增内容（新章节、新产品类别、新转介渠道），不破坏既有结构
- **PATCH**：内容修正、错别字、税务数字年度更新
