# Financial Services Repository

投资研究资料仓库 | Investment Research Repository

---

## 项目简介

本仓库用于存储和管理投资研究相关的财务模型、研究报告和分析文档。

---

## 目录结构

```
financial_services/
├── dcf_models/            # DCF 估值模型 (12家公司 + 汇总表)
├── reports/               # 研究报告 (Markdown格式)
├── docs/                  # 文档资源
│   └── assets/            # 静态资源
├── CLAUDE-FINANCIAL-SERVICES-ZH.md  # Claude 金融插件指南
└── INDEX.md               # 目录索引
```

---

## 内容概览

### DCF 估值模型

覆盖 12 家公司的 DCF 估值分析：

- **半导体/科技**：NVIDIA (NVDA)、TSMC (TSM)、Alphabet (GOOGL)、Tesla (TSLA)
- **光通信**：Applied Optoelectronics (AAOI)、Lumentum (LITE)
- **半导体材料/设备**：Aehr Test (AEHR)、AXT Inc (AXTI)
- **电信**：Nokia (NOKIA)
- **清洁能源**：Oklo (OKLO)、E-Energy
- **ETF**：VanEck Semiconductor ETF (SMH)

所有模型使用统一的 DCF 框架，包含 WACC 计算、自由现金流预测、敏感性分析。

### 研究报告

- 光模块行业投资分析报告
- 美股短期潜力分析

---

## 使用说明

### 查看 DCF 模型

```bash
cd dcf_models
open AAOI_DCF_Model.xlsx
```

### 使用 Claude 分析

```
# 分析特定公司的DCF模型
请分析 NVDA 的 DCF 模型，评估关键假设是否合理

# 进行可比公司分析
对比 AAOI 和 LITE 的估值水平

# 研究行业趋势
分析光模块行业的竞争格局和投资机会
```

### 更新日志

- **2026-05-10**：初始化仓库，创建目录结构
- 添加 12 个 DCF 估值模型
- 添加 2 篇研究报告
- 创建目录索引

---

## 相关资源

- [Claude Financial Services Plugin Guide](CLAUDE-FINANCIAL-SERVICES-ZH.md)
- [Directory Index](INDEX.md)

---

*Powered by Claude for Financial Services*