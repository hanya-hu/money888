# 海外华人版诊断和报告框架

本框架用于"海外华人投资美国市场"的访谈完成之后，输出完整的诊断报告。整个报告结构跟在美华人版**完全不同**，因为关注点不一样：海外华人版的核心问题不是退休账户和资产配置，而是 **estate tax 风险、合规账户、税务效率、持有结构**。

---

## 第 1 节：身份税务画像（中场）

收完 25 题后，先输出这一节作为中场报告，让用户确认基础判断对不对。

### 1.1 税务身份判定

把用户的身份归到下面其中一类：

- **NRA（Non-Resident Alien，标准海外华人）**：无 US 签证或绿卡，过去 3 年加权停留 <183 天。**绝大多数用户在这一类**。
- **疑似 substantial presence test 触发**：每年来美 4 个月以上的用户。提醒"你可能已经被 IRS 认定为 US tax resident，建议立刻找跨境 CPA 核实"。
- **持绿卡未放弃**：直接告诉用户"你不是 NRA，应该走美国华人版自检"。
- **特殊签证持有者**（H-1B、L-1、O-1 在美）：实际是 resident alien，应该走美国华人版自检。

### 1.2 适用的所得税协定

按用户居住国列：

- 中国大陆居民：**美中所得税协定有效**，股息预扣可降到 10%（默认 30%），需要 W-8BEN 申报
- 香港居民：**没有协定**，股息走 30%（HK 不在美中协定范围内）
- 加拿大居民：**美加协定**，股息 15%（不是 10%）
- 新加坡居民：**没有所得税协定**，股息 30%
- 英国居民：**美英协定**，股息 15%

### 1.3 是否有 estate tax 协定（极其重要）

- 中国：**没有**——这是几乎所有中国大陆海外华人用户的核心风险
- 加拿大：**有**——按 worldwide assets 比例享受 $15M 豁免一部分
- 英国：**有**——可以申请按 US citizen 同等的 $15M 豁免
- 澳大利亚：**有**
- 香港、新加坡：**没有**

如果用户是中国 / 香港 / 新加坡居民，**这是整个报告的中心议题**。

### 1.4 中场报告输出格式

```
## 你的身份税务画像

**税务身份**：[NRA / 疑似 SPT 触发 / 持绿卡 / 特殊签证]

**适用的所得税协定**：
- 美[国家]协定 [有效 / 无]
- 美股股息预扣应该是 [10% / 15% / 30%]
- 你之前提到 W-8BEN 是 [已交且有效 / 已交但过期 / 未交 / 不清楚]
- [如果未交：你账户的股息可能在按 30% 预扣，可以省 20 个百分点]

**estate tax 协定**：[有 / 没有]
- [如果没有：这意味着 NRA 标准 $60,000 estate tax 豁免完全适用，超过部分按 18%-40% 累进]
- [如果有：可以申请按 US citizen 的同等豁免（2026 是 $15M），但 worldwide 资产要披露]

**核心风险量级**：
- 当前美国 US-situs 资产合计：$X
- 超过 $60K 豁免部分：$Y
- 按最高税率 40% 估算的潜在 estate tax exposure：$Z
- （这是粗算，实际税率从 18% 开始累进，具体由跨境 CPA 算）

[暂停，等用户确认]
```

发完后问："这个身份税务画像跟你自己的理解一致吗？特别是 estate tax 这一块，你之前有思考过吗？"

---

## 第 2 节：US-Situs 资产快照

把用户在美国的所有资产分类列表。这一步的关键是把每项标注**是否算 US situs**（estate tax 触发器）。

### 2.1 US-Situs 资产清单（estate tax 适用）

| 资产类别 | 用户金额 | 是否 US situs | 备注 |
|---|---|---|---|
| 美股个股 | $X | ✅ 是 | 全部按市值计入 estate tax 基数 |
| 美国 ETF（VTI、VOO 等） | $X | ✅ 是 | RIC 算 US situs |
| 美国 mutual fund | $X | ✅ 是 | 同上 |
| 美国房产（个人持有） | $X | ✅ 是 | 永远是 US situs |
| 美国房产（LLC 持有） | $X | ✅ 是 | LLC 透明，仍 US situs |
| 美国房产（Foreign Corp 持有） | $X | ❌ 否 | Foreign Corp 股票不是 US situs |
| 加密（美国交易所） | $X | ⚠️ 争议 | IRS 未明确 |
| 加密（离岸 / 自托管） | $X | ❌ 否 | 通常不算 |
| 美国寿险死亡赔付 | $X | ❌ 否 | 关键例外，赔付不计入 |
| 美国年金 | $X | ✅ 是 | 当前 cash value 计入 |
| 美国私募 LP 份额 | $X | ✅ 通常是 | 视具体结构 |
| 美国合伙企业份额 | $X | ⚠️ 视情况 | 多数情况算 US situs |

**US-situs 资产合计**：$X
**Estate tax 触发金额（超过 $60K 豁免部分）**：$Y

### 2.2 非 US-Situs 资产清单（不计入 estate tax）

| 资产类别 | 用户金额 | 备注 |
|---|---|---|
| 美国银行存款（checking、savings） | $X | IRC §871(i) 利息免税且不算 US situs |
| 美国国债（直接持有） | $X | 不算 US situs |
| 本国资产 | $X | 完全不在美国税网内 |
| 第三地资产 | $X | 同上 |

### 2.3 估算 estate tax exposure

```
假设你今天身故的话，粗略估算：
- US-situs 资产总额：$X
- 减去 $60,000 豁免
- 应税基数：$Y
- 按累进税率（18% 起、$1M 以上 40%），估算税额约 $Z
- 占你 US 资产总额的比例：约 W%

这个数字是用来做"严重程度判断"，不是精确报税额。具体由 Form 706-NA 由 estate executor 在你身故 9 个月内申报。
```

### 2.4 三个关键红旗

按严重程度排，常见红旗：

- US-situs 资产 >$60K 但没有任何 estate planning 结构（最常见，最严重）
- 美国房产个人持有 + 受益人是 US person（双重风险：estate tax + 受益人 worldwide income）
- 持有美国 mutual fund / ETF 但本国对此类持仓有 PFIC 反向报告要求（部分国家会把 US-listed RIC 当作复杂金融产品征税）
- W-8BEN 没交，30% 股息预扣无谓损耗
- substantial presence test 即将触发但用户不自知

---

## 第 3 节：合规账户和资金路径

这一节给用户的"实操指引"，包括合规开户、资金汇入、文件提交。

### 3.1 NRA 友好的美国券商

主流选项（教育性列举，不构成推荐）：

| 券商 | 门槛 | 备注 |
|---|---|---|
| Interactive Brokers (IBKR) | 无最低 | NRA 友好程度最高，多币种、多市场 |
| Charles Schwab International | $25K+ | 客服中文，文件中英对照 |
| Firstrade | 无最低 | 华人友好，全中文界面 |
| TD Ameritrade（已并入 Schwab） | - | 旧客户保留账户，新开户走 Schwab |
| Tiger Brokers (老虎证券) | 视产品 | 港美股双轨，但要注意是否需要 W-8BEN |
| Futu (富途证券) | 视产品 | 同上 |

**Vanguard、Fidelity 国内版、E*TRADE** 一般不接受新的 NRA 开户。

### 3.2 必交的合规文件

- **W-8BEN**：申报 NRA 身份，享受协定优惠预扣率。每 3 年更新一次。
- **W-8BEN-E**：实体（公司、信托）版本
- **Certificate of Tax Residency**（本国出具）：申请协定优惠时备查
- **本国 ITIN**（如有）：填在 W-8BEN 第 6 行；没有的话填本国税号

### 3.3 资金汇入路径

- 中国大陆：每人每年 SAFE $50,000 限额，超过需要资金来源证明（工资、企业分红、不动产卖出）
- 香港、新加坡、加拿大：无资本管制，但银行可能要 KYC / SOF 文件
- 共同点：单笔超过 $10,000 美国银行会触发 CTR 报告（不是问题，只是合规流程）
- 不要做的事：通过亲友账户拼凑额度、地下钱庄、加密货币绕路（FATCA + FBAR 风险）

### 3.4 美国房产融资

NRA 在美国买房如果要贷款：

- 美国本地银行：HSBC、East West Bank、Cathay Bank 这类有大量华人客户的银行接受 NRA mortgage
- 利率比 US citizen 高 0.5%-1.5%
- 通常要求 30%-40% 首付（vs US citizen 20%）
- 必须有美国账户做月供
- 这一节不展开，建议用户找 mortgage broker 比对

---

## 第 4 节：税务效率优化

### 4.1 股息预扣优化

| 操作 | 当前状态 | 改善方向 |
|---|---|---|
| W-8BEN 提交 | [已交 / 未交 / 过期] | [立即提交或更新] |
| 实际股息预扣率 | [30% / 10% / 不知道] | 中国居民应该是 10%，验证券商 1099-DIV 等价表格 |
| 持仓里高股息资产比例 | [X%] | 长期 NRA 持仓应该减少高股息标的，转向低股息或 accumulating |

### 4.2 ETF 选择策略（针对 estate tax 和股息双重优化）

**用户面临的两难**：

- 用 US-listed ETF（VTI、VOO 等）→ 享受美国低费率 + 流动性，但 estate tax 风险 + 30%/10% 股息预扣
- 用 Ireland-domiciled ETF（CSPX、VWRA、VUAA 等）→ estate tax 不触发（不是 US situs）+ 内部累积式（accumulating）股息预扣 15% 而不是 30%，但需要欧盟或亚洲券商账户支持

**Ireland-domiciled 等价物（教育性参考）**：

| 美国 ETF | Ireland 等价 | 备注 |
|---|---|---|
| VOO（S&P 500） | CSPX、VUSA | 都是 accumulating 或 distributing，CSPX 累积式 |
| VTI（全美股） | VUAA、ITPS | |
| VXUS（除美国国际） | VWRA / SSAC | |
| BND（美债） | IDTL | |

**前提**：用户需要在 IBKR 或欧亚券商开 Ireland 产品账户（IBKR 可以买）。Schwab US、Firstrade 一般只能买美国 listed 产品。

### 4.3 美国租金收入的 §871(d) 选举

如果用户出租美国房产：

- 默认：30% gross rent withholding（最差选择，不能扣折旧、利息、维修）
- 选择 §871(d) ECI（Effectively Connected Income）：按 net basis 申报 1040-NR，可扣折旧、利息、保险、维修
- 通常 §871(d) ECI 对长期持有的出租房**显著更划算**
- 一旦做了选举，所有未来年度都按这个走，除非主动撤销

如果用户回答"不知道按哪种申报"，标记下来让 CPA 检查。

---

## 第 5 节：持有结构选项（核心议题）

这是海外华人版报告的核心。用户当前的持有结构 vs 几种替代结构的对比。

### 5.1 当前结构问题诊断

```
你现在的结构：[个人直接持有 / LLC 持有 / Foreign Corp 持有 / Trust 持有 / 其他]

问题：
- [如果个人直接持有 + US-situs 资产 >$60K]：直接 estate tax exposure
- [如果 LLC 持有美国房产]：LLC 透明，没解决 estate tax
- [如果已经是 Foreign Corp 持有]：方向对，但要看具体结构（美国房产 + Foreign Corp 还有 FIRPTA 和公司层税负的复杂度）
```

### 5.2 替代结构对比（仅作教育性介绍，最终方案必须由跨境 estate attorney 决定）

下面这些结构每一种都有具体的设立成本、税务陷阱、合规要求。本工具不替代律师做选择。

#### 选项 A：个人直接持有 + 美国寿险包裹

适合：US-situs 资产 $100K-$500K 的轻量用户

机制：
- 资产保留个人持有（简单）
- 同时购买一份美国 term life 寿险，保额覆盖估算的 estate tax exposure
- 寿险死亡赔付**不算 US situs**，可以用赔付来交 estate tax
- 受益人指定子女或本国继承人

成本：term life 年保费几千美元（取决于年龄健康）
缺点：寿险有年龄上限（通常 70-75 岁后费率高得不划算或买不到）

#### 选项 B：Foreign Corporation Holding（持有美国房产）

适合：美国房产 >$1M 的用户

机制：
- 在 BVI、开曼、香港、或本国注册一个 Foreign Corporation
- Foreign Corp 持有美国房产
- 用户持有 Foreign Corp 股票（不是 US situs）
- 身故时传的是 Foreign Corp 股票，没有 US estate tax

复杂度：
- 设立成本 $5K-$15K + 年度合规 $2K-$5K
- 公司层 corporate tax（美国房产租金按 21% federal 税）
- Branch profits tax（30%，可降到协定 5% 如果适用）
- FIRPTA 卖出预扣 15%（虽然 Foreign Corp 持股可避免个人层 FIRPTA）
- 不能享受自住房的 §121 exclusion（$250K/$500K 自住房卖出豁免）
- **这个结构对自住房通常不划算**，更适合纯出租房

#### 选项 C：Foreign Non-Grantor Trust

适合：US-situs 资产 >$2M 的用户

机制：
- 在境外设立 irrevocable foreign non-grantor trust
- Trust 持有美国资产
- 用户对 Trust 没有 grantor 控制权（关键，否则 IRS 会"穿透"）
- 受益人是子女或其他

复杂度极高：
- 设立成本 $15K-$50K
- Throwback tax 规则（NRA Trust 累积收益分配给 US person 受益人时有惩罚税）
- DNI（Distributable Net Income）规则
- 必须找跨境 estate attorney + 国际税务 CPA 联合搭建

#### 选项 D：把美国资产降到 $60K 以下

适合：用户**不愿意承受任何复杂度**

机制：
- 把 US-situs 资产降到 $60K 豁免内
- 其余资金放本国 / 第三地
- 投资美国市场的方式：通过本国券商买 ADR（部分美股有 ADR），或买 Ireland-domiciled ETF

缺点：放弃了直接投资美国市场的便利和品种丰富度

### 5.3 推荐路径（基于用户具体情况）

```
基于你的情况——
- US-situs 资产规模：$X
- 年龄：[Y]
- 受益人构成：[全 NRA / 全 US person / 混合]
- 复杂度承受：[简单 / 中等 / 复杂]
- 核心需求：[投资为主 / 房产为主 / 混合]

最贴合的路径方向是：[选项 A/B/C/D 中的一个或组合]

但具体方案必须由 [跨境 estate attorney + 国际税务 CPA] 联合搭建。本工具不替代他们的判断。
```

---

## 第 6 节：产品类别参考

引用 `references/overseas-product-library.md`。重点：NRA 友好产品和应避开的产品。

每次提到都附这段：

> **关于下面这些产品**：以下列出的都是公开理财教育资料里常被作为 NRA 投资者代表性选项的产品。出现在这里不构成对你的购买建议。具体选哪只、什么时候买、买多少、用哪个账户，需要你结合自己的居住地税务规则、券商可买性、长期判断决定。

---

## 第 7 节：专业服务转介清单

NRA 投资美国的专业服务地图跟美国华人版**不同**。下面列出关键人物。

### 7.1 必须找的专业人士（按用户具体情况触发）

| 触发条件 | 必须找的专业人士 |
|---|---|
| US-situs 资产 >$60K | 跨境 estate attorney（美国一边）|
| 美国房产持有 | 跨境 estate attorney + 国际税务 CPA |
| 子女是 US person 想做跨代规划 | estate attorney + 受益人国 tax advisor |
| 准备移民美国 | 移民律师 + 跨境税务 CPA（移民前 step-up basis 规划）|
| 计划用 Foreign Corp / Trust 结构 | estate attorney + 国际税务 CPA + 注册地 corporate counsel |
| 美国租金收入但没做 §871(d) 选举 | 国际税务 CPA |
| Substantial presence test 接近触发 | 国际税务 CPA（紧急）|
| 本国资产 + 美国资产 >$2M 且打算跨代传承 | estate attorney + 本国遗产律师双向协调 |

### 7.2 各类专业人士详情

#### 跨境 estate attorney（美国一边）

**做什么**：US estate tax 规划、Foreign Corp / Trust 结构搭建、跨境继承、Form 706-NA 申报指导、QDOT 设立。

**怎么找**：

- ACTEC（American College of Trust and Estate Counsel）会员：actec.org，搜 international estate planning 专长
- STEP（Society of Trust and Estate Practitioners）会员：step.org
- 大陆所跨境 private wealth group：Baker McKenzie、White & Case、Withers、Day Pitney
- 关键问候选人："Have you handled NRA clients from China / HK / SG with $X of US assets? What structures have you used?"

**预期费用**：

- 一次性咨询：$500-$1,500/小时
- 标准跨境 estate plan（含 will + trust + 持有结构建议）：$15,000-$50,000
- Foreign Corp / Trust 结构搭建：$25,000-$100,000+

#### 国际税务 CPA

**做什么**：1040-NR 报税、Form 706-NA estate tax 申报、§871(d) 选举、W-8BEN 优化、跨境双重征税避免、移民前 step-up planning。

**怎么找**：

- AICPA International Tax Section 成员目录
- 大四（Big Four）的跨境 private client team：Deloitte、PwC、EY、KPMG（费率高但覆盖全球）
- 中型专业所：US Tax Financial Services (USTAXFS)、Mazars、Withum
- 关键："Are you experienced with NRA clients from [my country]? Have you handled [substantial presence test transition / §871(d) elections / 706-NA filings]?"

**预期费用**：

- 简单 1040-NR 申报（仅股息利息）：$500-$1,500
- 含 §871(d) 净申报、多源所得、treaty benefits 的复杂申报：$2,000-$10,000
- 跨境规划咨询：$400-$700/小时

#### 本国 / 第三地的合作律师 / CPA

**做什么**：本国遗产规划必须跟 US 这边匹配，否则会出现"双重申报但豁免不衔接"的悲剧。

**怎么找**：

- 中国大陆：找做跨境业务的所（金杜、君合、中伦的 private wealth team）
- 香港：Withers、Bedell Cristin、Stephenson Harwood
- 新加坡：WongPartnership、Allen & Gledhill
- 让美国 estate attorney 推荐他们合作过的本国律师

#### 移民律师（如有移民规划）

**触发**：用户在 O18 提到 5-10 年内有移民意向。

**怎么找**：AILA（American Immigration Lawyers Association）会员

**关键提醒**：移民前的资产处置时间窗口对未来美国税负有巨大影响。一定要在拿到绿卡**之前**完成关键步骤（卖出本国低成本基础资产实现 step-up、把未来高增长资产转给非美籍家人等）。

#### 跨境财富经理（次优先）

**做什么**：日常资产管理 + 跨境账户协调。

**怎么找**：私人银行（HSBC Private、UBS、瑞士信贷、JP Morgan Private Bank、Citi Private）。注意私人银行通常**不做** estate tax 规划，他们是资产管理不是法律服务。

### 7.3 不要找的人

- 国内的"美国房产投资顾问"通常是 broker 拿佣金，不会告诉你 estate tax 风险
- 普通会计师（不懂跨境）做 1040-NR 高错误率
- 综合性 wealth manager 但没有跨境经验的
- 任何承诺"我们能让你 0 美国税"的人

---

## 第 8 节：未来 90 天行动清单

跟美国华人版一样的格式，但内容**只放用户自己能直接执行的事**，复杂的结构搭建放第 7 节专业服务清单。

典型的自助执行类行动：

- 提交或更新 W-8BEN（5 分钟，去券商网站后台）
- 检查券商账户的实际股息预扣率（5 分钟，看 1099 等价表格）
- 把美国房产租金从 30% gross 改成 §871(d) ECI 申报（要 CPA，但用户先收集房产 cost basis、折旧记录、所有费用收据）
- 整理一份"美国资产清单 + 受益人指定"的文档（30 分钟）
- 如果当前账户里有美国 mutual fund，考虑替换为同等 ETF（mutual fund 比 ETF 在 NRA estate tax 触发上更糟糕，ETF 至少比较容易处置）

90 天清单不超过 5 项。

---

## 第 9 节：完整免责声明

报告末尾贴这段：

> ---
>
> **重要声明**
>
> 本报告基于你提供的数据和公开理财教育常识生成，仅作个人自我整理和教育用途使用。
>
> 报告作者不是注册的财务规划师 (CFP)、投资顾问、税务师 (CPA / EA) 或律师。报告中提到的任何 ETF、共同基金、税优工具、持有结构、申报操作，都不是针对你个人的购买建议或法律建议。
>
> **海外华人投资美国市场涉及多个司法辖区的法律和税务规则，错一步代价可能是数十万美元的额外税负**。实际操作之前，必须就以下事项咨询持牌专业人士：
>
> - US-situs 资产 >$60K 的 estate tax 规划方案
> - Foreign Corporation / Foreign Trust 结构的设立细节
> - W-8BEN 提交和 treaty benefits 申请
> - §871(d) 净基础租金申报选举
> - Substantial presence test 是否触发
> - 移民前的 step-up basis 规划时点
> - 本国遗产规则跟美国 estate tax 的协调
> - 任何让你睡不好觉的决定
>
> 跨境税务规则会随两国法律变化而变化。本报告写作时点的关键数字：
> - NRA estate tax exemption $60,000（IRC §2102(b)）
> - 默认 NRA 股息预扣率 30%（IRC §1441）
> - 美中所得税协定股息优惠率 10%（1984 年协定，仍有效）
> - 美中**没有** estate tax treaty
>
> 这些数字使用前请向跨境 CPA 核实最新版本。
>
> 数据完整性：本报告基于你访谈中提供的信息。如果某项资产、负债或身份信息没有报准，结论可能偏差。建议每年重新做一次自检，特别是在身份发生变化（签证、移民、居住地切换）时立刻重做。

---

## 附：海外华人版报告完整结构索引

一份完整报告的输出顺序：

1. 开场免责声明（在 SKILL.md 路径分流后开场白里）
2. 身份税务画像（第 1 节）
3. US-Situs 资产快照 + 三个红旗（第 2 节）
4. **暂停，等用户确认**
5. 合规账户和资金路径（第 3 节）
6. 税务效率优化（第 4 节）
7. 持有结构选项对比（第 5 节）
8. 产品类别参考（第 6 节）
9. 专业服务转介清单（第 7 节）
10. 自助执行类 90 天行动清单（第 8 节）
11. 完整免责声明（第 9 节）
