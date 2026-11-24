中文 | [English](README_EN.md) | [日本語](README_JA.md)

# AI Berkshire - AI 时代的价值投资研究框架

> "Price is what you pay, value is what you get." — Warren Buffett
>
> 用 AI 重新定义投资研究的深度与效率。

**AI Berkshire** 是一套同时兼容 Claude Code 与 Codex 的投资研究 Skill 合集，将巴菲特、芒格、段永平、李录四位价值投资大师的方法论系统化、结构化，通过 AI Agent 做专业级投资研究。

一个人 + Claude Code / Codex = 一个投研团队。

本仓库基于上游框架 fork，已清空上游研究报告与个人展示内容，用作本地投研工作台。新报告写入 `reports/` 后，运行 `python3 tools/reports_index.py` 刷新索引。

<!-- REPORTS-BANNER:START 由 tools/reports_index.py 自动更新，勿手改 -->

> 📖 **想读报告，用 [阅读站](https://xbtlin.github.io/ai-berkshire/)**：成品报告按公司、专题、时间整理，电脑和手机都好读，可搜索、记住阅读进度。
>
> 📊 全部 0 份报告（含底稿）· 0 家公司 · 0 个专题，GitHub 上的完整目录见 [研究报告索引](reports/README.md)，更新至 —。

<!-- REPORTS-BANNER:END -->

[为什么不能直接问 AI](#为什么不能直接问-ai) · [Skills 一览](#skills-一览22个) · [快速开始](#快速开始) · [研究索引](reports/README.md) · [设计理念](#设计理念)

---

## 为什么不能直接问 AI？

直接问模型「某公司值不值得买」，通常会得到两面讨好的分析，最后以「投资有风险」收尾。看起来完整，但很难据此做决策。

AI Berkshire 解决的是**分析质量与决策纪律**：

1. **强制给结论**：通过 / 不通过 / 灰色地带，并给出价格观察线，不打太极。
2. **四大师视角对抗**：段永平（生意）/ 巴菲特（估值）/ 芒格（逆向）/ 李录（长期）互相挑战，而不是单一 prompt 拼贴。
3. **结构化反偏见**：信息丰富度 A/B/C、逆向检验、快速否决清单、反共识检查、留白原则。
4. **金融计算可核验**：市值、PE、情景估值等用 `tools/financial_rigor.py` 做精确十进制计算，关键数据至少两源交叉。
5. **流程可复现**：同样输入 → 结构与深度一致的输出，便于横向对比与前后跟踪。
6. **多 Agent 并行**：`/investment-team` 等会并行调度多个研究视角，再由 Team Lead 综合。

<p align="center">
  <img src="assets/team-core.svg" alt="Team Lead 并行调度四大师 Agent" width="720" />
</p>

> **普通人问 AI 得到的是「看起来对的分析」；用本框架得到的是「可以拿来做决策的投研报告」。**

---

## 整体架构

<p align="center">
  <img src="assets/architecture.svg" alt="AI Berkshire 整体架构" width="760" />
</p>

- **Skill 层**：22 个明确入口——深度研究、财报、行业筛选、持仓管理、思维工具
- **Agent 层**：团队型 skill 由 Team Lead 并行调度多视角 Agent；轻量 skill 直连工具
- **工具层**：精确计算、检索、报告抽检，保证数据可验证

---

## Skills 一览（22个）

### 🔬 深度研究类

| Skill | 用途 | 适合场景 |
|-------|------|---------|
| [`/investment-research`](skills/investment-research.md) | 四大师综合深度分析 | 对一家上市公司做全方位投资研究 |
| [`/company-valuation`](skills/company-valuation.md) | 公司内在价值与估值复核 | 现金流、SOTP、反向估值与可复算验证 |
| [`/investment-team`](skills/investment-team.md) | 多 Agent 并行投研团队 | 4 个 Agent 并行研究，再综合研判 |
| [`/management-deep-dive`](skills/management-deep-dive.md) | 管理层纵深研究 | 管理层是核心变量时深挖 |
| [`/private-company-research`](skills/private-company-research.md) | 未上市公司深度研究 | 信息稀缺的未上市公司 |
| [`/deep-company-series`](skills/deep-company-series.md) | 长文系列拆一家公司 | 从认知重置到决策闭环的深度系列 |

### 📊 财报分析类

| Skill | 用途 | 适合场景 |
|-------|------|---------|
| [`/earnings-review`](skills/earnings-review.md) | 财报精读（一手资料） | 只读原始财报，不依赖二手研报 |
| [`/earnings-team`](skills/earnings-team.md) | 财报精读团队 | 四大师并行解读 → 可发布文章 |

### 🏭 行业筛选类

| Skill | 用途 | 适合场景 |
|-------|------|---------|
| [`/industry-research`](skills/industry-research.md) | 产业链全景扫描 | 按产业链环节切片研究投资机会 |
| [`/industry-funnel`](skills/industry-funnel.md) | 行业漏斗筛选 | 全市场 → 粗筛 ≤10 家 → 终选 3 家 |
| [`/quality-screen`](skills/quality-screen.md) | 去劣筛选（7 条硬指标） | 快速排除非一流公司 |
| [`/bottleneck-hunter`](skills/bottleneck-hunter.md) | 供应链瓶颈猎手 | 寻找产业链物理瓶颈与套利机会 |
| [`/era-alpha`](skills/era-alpha.md) | 时代 α 捕手 | 识别高增长主线中的核心 α |
| [`/investment-checklist`](skills/investment-checklist.md) | 巴菲特买入前 Checklist | 六关快速筛选 |

### 📈 持仓管理类

| Skill | 用途 | 适合场景 |
|-------|------|---------|
| [`/income-investment`](skills/income-investment.md) | 收益型股票分析 | 区分可持续收益与收益率陷阱 |
| [`/portfolio-review`](skills/portfolio-review.md) | 组合管理与优化 | 仓位、集中度、再平衡 |
| [`/thesis-tracker`](skills/thesis-tracker.md) | 投资论文追踪 | 买入后持续跟踪论文是否被证伪 |
| [`/thesis-drift`](skills/thesis-drift.md) | 投资论文漂移检测 | 区分事实变化、估值变化与措辞变化 |
| [`/news-pulse`](skills/news-pulse.md) | 股价异动快速归因 | 10 分钟搞清「发生了什么」 |

### 🧠 思维工具类

| Skill | 用途 | 适合场景 |
|-------|------|---------|
| [`/dyp-ask`](skills/dyp-ask.md) | 段永平问答 | 以段永平的方式思考商业、投资、人生 |
| [`/financial-data`](skills/financial-data.md) | 财务数据获取与交叉验证规范 | 关键数据两源校验 |
| [`/wechat-article`](skills/wechat-article.md) | 公众号文章协作 | 作者 / 编辑 / 读者三 Agent 协作 |

---

## 快速开始

### 成本与模型选择

深度投研类 Skill 会多轮研究、交叉验证和多 Agent 综合，token 消耗较高。真实投资决策中的关键判断，优先用更强模型；轻量模型更适合初筛、摘要。想控制成本时，先用 [`/quality-screen`](skills/quality-screen.md) 或 [`/news-pulse`](skills/news-pulse.md)，值得深入再上 [`/investment-research`](skills/investment-research.md) / [`/investment-team`](skills/investment-team.md)。

### 1. 安装 AI 客户端

Claude Code：

```bash
npm install -g @anthropic-ai/claude-code
```

Codex：

```bash
curl -fsSL https://chatgpt.com/codex/install.sh | sh
# 或: npm install -g @openai/codex
# 或: brew install --cask codex
codex --version
```

如需减少 Claude Code 逐次授权确认（仅在可信环境）：

```bash
claude --dangerously-skip-permissions
```

### 2. 安装 Skills

```bash
git clone https://github.com/zqiong6/ai-berkshire.git
cd ai-berkshire

# Claude Code
./scripts/install-claude-commands.sh

# Codex
./scripts/install-codex-skills.sh
# 可选 slash prompts
./scripts/install-codex-prompts.sh
```

Windows 对应 `scripts/*.bat`。仓库入口：`skills/*.md`（Claude 源）→ `codex-skills/`（由 sync 脚本生成）→ `codex-prompts/`（可选兼容层）。

### 3. 使用示例

Claude Code：

```bash
/investment-research 腾讯
/investment-team 美团
/earnings-review 腾讯 2025Q4
/industry-funnel AI算力
/portfolio-review 腾讯30%, 美团20%, 现金50%
/news-pulse 腾讯
```

Codex：

```text
使用 investment-research 研究腾讯
使用 industry-funnel 筛选 AI算力
```

若安装了 slash prompts：

```text
/prompts:investment-research 腾讯
```

### 4. 写报告与刷新索引

```bash
# 报告放入 reports/{公司或专题}/
git add -- reports/
python3 tools/reports_index.py
git add -- README.md reports/README.md reports/index.json
```

只检查索引是否过期：

```bash
python3 tools/reports_index.py --check
```

---

## 实战研究报告

<!-- REPORTS-INDEX:START 由 tools/reports_index.py 自动更新，勿手改 -->

**📊 [全部研究索引 →](reports/README.md)** ｜ 0 份报告 · 0 家公司 · 0 个专题 · 更新至 —

最近更新：

| 日期 | 报告 | 归属 |
|------|------|------|

<!-- REPORTS-INDEX:END -->

---

## 设计理念

### 四大师方法论融合

**段永平 ·「对的生意」**——商业模式本质，是其余三个视角的共同起点：

| 巴菲特 | 芒格 | 李录 |
|:---:|:---:|:---:|
| 护城河<br>安全边际<br>管理层 | 逆向思考<br>风险清单<br>偏误自查 | 文明趋势<br>范式转移<br>产业价值 |

四位大师被设计成互相挑战：好生意是否够深？够便宜是否还值得长期持有？

### 金融严谨性工具 (`tools/financial_rigor.py`)

| 功能 | 命令 | 解决的问题 |
|------|------|-----------|
| 市值验算 | `verify-market-cap` | 股价 × 总股本，检测单位错误 |
| 估值验算 | `verify-valuation` | PE / PB / ROE / FCF Yield |
| 多源交叉验证 | `cross-validate` | 多来源比对，超容差告警 |
| 三情景估值 | `three-scenario` | 乐观 / 中性 / 悲观目标价 |
| Benford 检测 | `benford` | 首位数字分布异常 |
| 精确计算器 | `calc` | 任意财务表达式，替代 LLM 心算 |

所有计算使用 `decimal.Decimal`，不用 `float`。

专门估值可调用 `/company-valuation`；方法说明见 [`tools/valuation/`](tools/valuation/)。

---

## 免责声明

本项目仅供学习和研究，不构成任何投资建议。投资有风险，决策需谨慎。请始终做好自己的尽职调查（DYOR）。

## License

MIT License

> "The best investment you can make is in yourself." — Warren Buffett
