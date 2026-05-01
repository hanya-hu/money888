# 安装和使用说明

MONEY888 是一个 Claude Skill，可以通过几种不同方式使用。

---

## 方式一：在 Claude.ai（网页版 / 桌面端 / 移动端）使用

### 适用人群

绝大多数用户。Claude Pro / Team / Enterprise 订阅都支持上传 Skill。

### 步骤

#### 1. 下载或自行打包 SKILL 文件

**选项 A：从 Releases 下载现成的 .skill 文件**

去本仓库的 [Releases](../../releases) 页面，下载最新版本的 `money888.skill` 文件。

**选项 B：自行用 Anthropic 官方脚本打包**

```bash
# 1. clone 本仓库
git clone https://github.com/hanya-hu/money888.git
cd money888

# 2. clone Anthropic 官方的 skill-creator（包含打包脚本）
git clone https://github.com/anthropics/skills /tmp/anthropic-skills

# 3. 运行打包脚本
cd /tmp/anthropic-skills/skill-creator
python -m scripts.package_skill /path/to/money888 ./
# 输出 money888.skill 文件
```

#### 2. 上传到 Claude.ai

1. 打开 Claude.ai，登录账号
2. 进入 Settings → Capabilities → Skills（或同等位置）
3. 点击 "Upload Skill" 或类似按钮
4. 选择刚才下载或生成的 `money888.skill` 文件
5. 等待上传完成

#### 3. 启用并使用

1. 在新对话里，确认 MONEY888 这个 Skill 已经启用
2. 跟 Claude 说：
   - "帮我做个财务自检"
   - "用 MONEY888 给我做个理财规划"
   - "我想做一次系统的财务体检"
   - 海外用户可以说："我在 [国家] 想投资美国市场，帮我做个 NRA 财务规划"
3. Claude 会自动加载 MONEY888 并开始路径分流（A 在美华人 / B 海外华人）

---

## 方式二：在 Claude Code 命令行使用

### 适用人群

开发者、技术用户，喜欢用命令行的人。

### 步骤

```bash
# 1. clone 仓库
git clone https://github.com/hanya-hu/money888.git
cd money888

# 2. 把整个目录复制到 Claude Code 的 skills 目录
mkdir -p ~/.claude/skills/money888
cp SKILL.md ~/.claude/skills/money888/
cp -r references ~/.claude/skills/money888/

# 3. 在 Claude Code 里启动一个新会话
claude

# 4. 让 Claude Code 加载 SKILL
> 启用 money888 这个 skill 帮我做财务自检
```

---

## 方式三：手动用作 Prompt（不依赖 Claude.ai 的 Skill 框架）

### 适用人群

- 用 Claude API 直接开发
- 用 ChatGPT、Gemini 或其他 LLM
- 或者当前账号没有 Claude.ai Skills 功能

### 步骤

#### 1. 把 SKILL.md 当作系统 prompt 的一部分

直接复制 `SKILL.md` 的全部内容到对话开头，或者作为 API 调用的 system prompt。

#### 2. 让 LLM 按需读取参考文件

由于没有自动加载机制，你需要按 SKILL.md 的指引手动提供参考文件内容：

- 用户选轨道 A 时，把 `references/question-bank.md` 全文粘进对话
- 中场诊断阶段，把 `references/frameworks.md` 第 1 节粘进去
- 报告阶段，把 `references/frameworks.md` 第 2-7 节 + `references/product-library.md` 粘进去

轨道 B 类似，用 `overseas-` 前缀的文件。

#### 3. 上下文窗口

- 完整的轨道 A 文件加起来约 50KB tokens
- 完整的轨道 B 文件加起来约 45KB tokens
- Claude 4.x、GPT-4 Turbo+、Gemini 1.5+ 都能处理

如果上下文不够，分阶段加载（访谈阶段不需要 frameworks，诊断阶段才需要）。

---

## 给本仓库 contributors 的额外说明

如果你在本地开发或测试 SKILL，建议用 `git config` 设置局部匿名信息：

```bash
cd money888
git config user.name "MONEY888 Contributor"
git config user.email "anonymous@money888.local"
```

这样你的 commit 不会带个人信息。

---

## 常见问题

**Q：为什么我用了 Skill 之后 Claude 没有触发它？**

A：Skill 触发依赖 description 里的关键词。试着说"帮我做财务自检"或"用 MONEY888 给我规划"。如果还是不触发，可能是 Skill 没有正确启用，去 Settings 里检查。

**Q：访谈中途想退出怎么办？**

A：直接说"我先停一下"或"不做了"。Claude 会停下访谈。下次想继续，新开对话重新开始就好（除非你有 memory 功能保留了上次进度）。

**Q：我可以只走一部分访谈吗？**

A：可以。但报告质量会下降，因为某些诊断需要交叉验证多个数据点。建议至少完成第一到第三部分（基本情况、现金流、资产盘点）。

**Q：海外华人和在美华人 hybrid 情况怎么办？**

比如持绿卡但人在中国，或者准备明年移民美国的人——SKILL.md 第零阶段的"路径分流"会处理这些情况，根据具体身份给判定。模糊情况会建议先找跨境 CPA 确认税务身份再回来用工具。

**Q：工具会不会保留我的隐私数据？**

A：本工具是开源 markdown 文件集合，没有任何数据后端。你的所有访谈数据都在 Claude.ai（或你使用的 LLM 平台）的对话上下文里，不会被工具维护者看到。但是，**你使用的 LLM 平台本身有自己的数据政策**——比如 Anthropic 是否保留对话用于改进模型，请去看对应平台的隐私条款。

**Q：可以中途切换轨道吗？**

A：不能。两条轨道的访谈题目设计完全不同。如果开场选错了，需要重开一个对话从头来过。

---

## 反馈和报告问题

发现内容错误（特别是税务数字过时、法条引用错误）或想提改进建议：

- 提 [GitHub Issue](../../issues)
- 提交 Pull Request（先看 [CONTRIBUTING.md](./CONTRIBUTING.md)）

不接受针对个人的财务咨询。
