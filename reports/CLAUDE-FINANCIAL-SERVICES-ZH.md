# Claude for Financial Services 使用指南

## 概述

**Claude for Financial Services** 是 Anthropic 官方推出的金融服务业插件市场，专为投资银行、股票研究、私募股权和财富管理等工作流程设计。

> [!IMPORTANT]
> 本仓库中的任何内容均不构成投资、法律、税务或会计建议。这些 agent 会起草分析师工作成果（模型、备忘录、研究笔记、对账等），供合格专业人士审核。它们不会做出投资建议、执行交易、绑定风险、过账到账本或批准入职；所有输出都需人工签字确认。您有责任验证输出结果，并确保符合适用于您公司的法律法规。

---

## 安装方式

### 方式一：Claude Code 命令行安装

```bash
# 添加市场
claude plugin marketplace add anthropics/financial-services

# 核心技能 + 连接器（建议首先安装）
claude plugin install financial-analysis@claude-for-financial-services

# 命名 Agent - 按需选择
claude plugin install pitch-agent@claude-for-financial-services
claude plugin install gl-reconciler@claude-for-financial-services
claude plugin install market-researcher@claude-for-financial-services
claude plugin install earnings-reviewer@claude-for-financial-services
claude plugin install model-builder@claude-for-financial-services
claude plugin install kyc-screener@claude-for-financial-services
claude plugin install valuation-reviewer@claude-for-financial-services
claude plugin install month-end-closer@claude-for-financial-services
claude plugin install statement-auditor@claude-for-financial-services

# 垂直技能包
claude plugin install investment-banking@claude-for-financial-services
claude plugin install equity-research@claude-for-financial-services
claude plugin install private-equity@claude-for-financial-services
claude plugin install wealth-management@claude-for-financial-services
claude plugin install fund-admin@claude-for-financial-services
claude plugin install operations@claude-for-financial-services
```

### 方式二：手动安装

已安装的市场路径：`~/.claude/plugins/marketplaces/claude-for-financial-services`

---

## 核心 Agent 一览

| 功能 | Agent | 用途 |
|------|-------|------|
| **投顾** | Pitch Agent | 可比公司、先例分析、LBO → 品牌PPT，端到端 |
| | Meeting Prep Agent | 每次客户会议前的简报包 |
| **研究与建模** | Market Researcher | 行业概览、竞争格局、同行对比、想法清单 |
| | Earnings Reviewer | 财报电话 + 文件 → 模型更新 → 笔记草稿 |
| | Model Builder | DCF、LBO、三表模型、可比公司 - 直接在 Excel 中操作 |
| **基金行政** | Valuation Reviewer | 吸收GP包、运行估值模板、准备LP报告 |
| | GL Reconciler | 查找差异、追溯根本原因、流转审批 |
| | Month-End Closer | 计提、滚动、差异说明 |
| | Statement Auditor | 审计LP报表后再分发 |
| **运营** | KYC Screener | 解析入职文档、运行规则引擎、标记缺口 |

---

## 垂直插件详解

### financial-analysis（核心）⭐ 推荐首先安装
**核心财务建模与分析工具**，包含所有11个数据连接器。

| 斜杠命令 | 功能 |
|---------|------|
| `/comps` | 可比公司分析，含交易倍数 |
| `/dcf` | DCF估值，含WACC和敏感性分析 |
| `/lbo` | 杠杆收购模型 |
| `/3-statement-model` | 三表财务模型填充 |
| `/debug-model` | Excel模型审计 - 公式追踪、硬编码检测、余额核对 |
| `/competitive-analysis` | 竞争格局与市场定位 |
| `/ppt-template` | 创建可复用的PPT模板 |

### investment-banking（投资银行）
**投行生产力工具** - 客户和市场洞察、PPT创建、财务分析、交易管理。

| 斜杠命令 | 功能 |
|---------|------|
| `/one-pager` | 一页公司概况（Pitch Book用） |
| `/cim` | 起草保密信息备忘录（CIM） |
| `/teaser` | 匿名一页公司概要 |
| `/buyer-list` | 战略和财务买家范围 |
| `/merger-model` | 合并收购增厚/稀释分析 |
| `/process-letter` | 竞标说明和流程函 |
| `/deal-tracker` | 跟踪进行中的交易、里程碑和待办事项 |

### equity-research（股票研究）
**股票研究工具** - 覆盖和发布工作流程。

| 斜杠命令 | 功能 |
|---------|------|
| `/earnings` | 财报后季度更新报告 |
| `/earnings-preview` | 财报前情景分析和关键指标 |
| `/initiate` | 机构级首次覆盖报告 |
| `/model-update` | 用新数据更新财务模型 |
| `/morning-note` | 晨会笔记和交易思路 |
| `/sector` | 行业概览和主题报告 |
| `/thesis` | 维护和更新投资论点 |
| `/catalysts` | 跟踪覆盖范围内的即将到来的催化剂 |
| `/screen` | 股票筛选和想法来源 |

### private-equity（私募股权）
**私募股权工具** - 从项目发现到投资决策。

| 斜杠命令 | 功能 |
|---------|------|
| `/source` | 发现公司、检查CRM、起草创始人联系 |
| `/screen-deal` | 对收到的CIM和概要进行快速筛选 |
| `/dd-checklist` | 各工作流的尽职调查清单 |
| `/dd-prep` | 管理层演示和专家通话准备 |
| `/unit-economics` | ARR队列、LTV/CAC、净保留率、收入质量 |
| `/returns` | IRR/MOIC敏感性表 |
| `/ic-memo` | 投资委员会备忘录起草 |
| `/portfolio` | 跟踪投资公司KPI和差异 |
| `/value-creation` | 投后100天计划和EBITDA桥梁 |
| `/ai-readiness` | 评估投资组合公司的AI就绪程度 |

### wealth-management（财富管理）
**财富管理和财务咨询工具**。

| 斜杠命令 | 功能 |
|---------|------|
| `/client-review` | 客户会议准备，含业绩和话题要点 |
| `/financial-plan` | 退休、教育、遗产和现金流预测 |
| `/rebalance` | 配置漂移分析和税务优化再平衡 |
| `/client-report` | 客户对账单 |
| `/proposal` | 潜在客户提案 |
| `/tlh` | 识别税务亏损收割机会并管理洗售规则 |

### fund-admin（基金行政）
**基金管理和财务运营工具**。

GL对账、差异追溯、计提、滚动、差异说明、NAV结算

### operations（运营）
**运营工作流**：KYC文档解析和规则评估

### 合作伙伴插件

| 插件 | 功能 |
|------|------|
| **lseg** | 债券估值、互换曲线、FX套利、期权波动率、LSEG数据的宏观利率监控 |
| **sp-global** | S&P Capital IQ - 公司概况、财报预览、融资摘要 |

---

## MCP 数据连接器

financial-analysis 核心插件中集中了所有连接器，可连接以下数据源：

| 提供商 | 说明 |
|--------|------|
| Daloopa | 文档和数据提取 |
| Morningstar | 晨星数据 |
| S&P Global | S&P Capital IQ |
| FactSet | FactSet数据 |
| Moody's | 穆迪数据 |
| MT Newswires | 新闻电线 |
| Aiera | 财报电话会议 |
| LSEG | LSEG金融数据 |
| PitchBook | 私募股权数据 |
| Chronograph | 另类投资数据 |
| Egnyte | 文档管理 |

> 注意：MCP访问可能需要提供商的订阅或API密钥。

---

## 使用方法

### 1. 斜杠命令
安装后，在对话中直接使用斜杠命令：
```
/comps AAPL GOOGL MSFT
/dcf 台积电
/earnings 苹果 2024Q1
```

### 2. 自然语言任务
直接描述您的任务：
- "帮我分析Netflix和迪士尼的可比公司"
- "为这笔LBO交易构建一个简单的DCF模型"
- "准备一个科技行业竞争格局分析"
- "审核这份PPT，确保数据一致性"

### 3. Agent 调度
安装的 Agent 会在 Cowork 中自动出现，可直接调用端到端工作流。

---

## 自定义配置

这些是参考模板，可根据您公司的工作流程进行调整：

1. **更换连接器** - 修改 `.mcp.json` 指向您的数据提供商和内部系统
2. **添加公司背景** - 将您的术语、流程和格式标准放入技能文件
3. **使用您的模板** - `/ppt-template` 教 Claude 您的品牌PPT布局
4. **调整 Agent 范围** - 编辑 `agents/<slug>.md` 以匹配团队实际工作流程
5. **添加自己的工作流** - 复制现有结构来创建我们尚未覆盖的工作流

---

## 故障排除

### 插件未显示
1. 重启 Claude Code
2. 运行 `/plugins` 检查已安装插件列表
3. 确认 marketplace 已正确添加

### MCP 连接失败
- 检查 API 密钥是否配置
- 确认数据提供商的订阅状态
- 验证网络连接和代理设置

### 命令不识别
- 确认插件已正确安装并启用
- 尝试使用完整格式：`/plugin:command-name`

---

## 插件结构

```
plugins/
├── agent-plugins/        # 命名 Agent（自包含插件）
├── vertical-plugins/     # 按 FSI 垂直分类的技能和命令
└── partner-built/        # 合作伙伴插件（LSEG, S&P Global）
```

所有内容均为文件形式（Markdown 和 JSON），无需构建步骤。

---

## 获取帮助

- 查看原始 README：`~/.claude/plugins/marketplaces/claude-for-financial-services/README.md`
- 插件开发：`~/.claude/plugins/marketplaces/claude-for-financial-services/CLAUDE.md`
- Claude Code 插件文档：运行 `/help`

---

*本插件市场由 Anthropic 官方维护，采用 Apache License 2.0 开源许可。*