# Visualizing Development with WBGAPI

## Project Overview
This project builds a macroeconomic visualization pipeline using the World Bank API (`wbgapi`) to evaluate the development trajectory of Guatemala from 2000 onward. The notebook collects, cleans, transforms, and visualizes key economic indicators in order to move beyond a simple “growth story” and assess broader development performance.

Rather than relying on a single metric, this project studies Guatemala through multiple dimensions of macroeconomic performance: output growth, living standards, labor market conditions, inflation, fiscal balance, trade balance, and the savings–investment relationship.

## Objective
The objective of this project is to answer a simple but important question:

**Has Guatemala’s economic growth translated into broader and more balanced development?**

To answer this, the notebook compares Guatemala not only to its own historical trend, but also to benchmark groups such as the world average and upper-middle-income economies. This allows the analysis to distinguish between absolute growth and relative development progress.

## Data Source
- **Source:** World Bank Open Data
- **API Library:** `wbgapi`
- **Time Period:** 2000–2024
- **Countries / Benchmark Groups:**
  - Guatemala (`GTM`)
  - Upper Middle Income (`UMC`)
  - World (`WLD`)

## Indicators Used
The project uses the following indicators:

- Real GDP per capita
- Labor force participation rate
- Unemployment rate
- Total labor force
- Real GDP
- CPI inflation
- Gross domestic savings
- Gross capital formation
- Exports (% of GDP)
- Imports (% of GDP)
- Tax revenue (% of GDP)
- Government expenditure (% of GDP)

## Methodology
The notebook follows a four-step workflow:

### 1. Data Ingestion
Using `wbgapi`, the notebook fetches live macroeconomic series directly from the World Bank database. This creates a reproducible workflow instead of relying on manually downloaded spreadsheets.

### 2. Data Cleaning and Structuring
The raw API output is reshaped into a time-series DataFrame, with years as the index and indicators as columns. A Guatemala-only analytical subset (`df_gtm`) is then created for focused analysis.

### 3. Feature Engineering
Several derived indicators are constructed to support interpretation:

- **Natural unemployment rate:** 5-year rolling average of unemployment
- **Productivity proxy:** Real GDP divided by total labor force
- **Trade balance proxy:** Exports minus imports
- **Fiscal balance proxy:** Tax revenue minus government expenditure

### 4. Visualization and Executive Dashboard
The notebook develops a sequence of charts and concludes with a **2x3 executive dashboard** summarizing Guatemala’s macroeconomic profile:
- Real GDP
- Inflation
- Unemployment
- Fiscal balance
- Trade balance
- Savings vs. investment

## Key Findings

### 1. Growth Is Real, but the Development Story Is More Complicated
Guatemala’s real GDP and GDP per capita both increased over time, indicating that the economy did expand in absolute terms.

### 2. Benchmarking Changes the Interpretation
When Guatemala is compared against the world average and upper-middle-income economies, the apparent success of GDP per capita growth becomes less impressive. The country shows improvement, but not strong convergence.

### 3. Output Growth Does Not Automatically Mean Broad Prosperity
The notebook distinguishes between total output growth and improvements in living standards. This highlights that aggregate GDP expansion alone is not enough to conclude that development is inclusive or substantial.

### 4. Labor Market Conditions Require a Multi-Metric View
Unemployment and labor force participation are analyzed together to provide a fuller picture of labor market performance. A low unemployment rate alone may hide structural weakness if labor force participation is unstable or weak.

### 5. External and Fiscal Constraints Remain Important
Trade and fiscal balance visualizations suggest that Guatemala faces persistent structural pressures. These imbalances matter because they affect long-run sustainability and the ability to finance growth.

### 6. Savings and Investment Gaps Matter for Development
Comparing domestic savings with capital formation helps evaluate whether growth is being financed internally or depends on external resources. This provides a deeper perspective on development capacity beyond headline GDP growth.

## Executive Takeaway
This project shows that **economic growth and economic development are not the same thing**. Guatemala experienced measurable expansion in output, but a broader dashboard perspective reveals a more mixed picture: limited relative convergence, labor market frictions, and persistent macroeconomic imbalances.

In short, the notebook argues that a country should not be evaluated by GDP growth alone. Development must be assessed through a wider macroeconomic lens.

## Tech Stack
- Python
- `wbgapi`
- `pandas`
- `matplotlib`
- `seaborn`

## Deliverable
The final deliverable is a multi-panel executive dashboard titled:

**Guatemala Economic Snapshot**

This dashboard is designed to communicate the country’s macroeconomic condition in a concise and visually accessible format.
# 危地马拉宏观经济可视化分析项目

## 项目简介
本项目基于 Python 与 World Bank API（`wbgapi`）搭建了一套宏观经济数据抓取、清洗、分析与可视化流程，对危地马拉 2000–2024 年的经济表现进行多维度评估。项目重点不局限于 GDP 增长，而是结合就业、通胀、财政、外贸、储蓄与投资等指标，构建更完整的经济画像。

## 项目目标
- 搭建可复用的国际宏观经济数据分析流程
- 从多个维度评估危地马拉的发展表现
- 通过数据可视化输出适合展示和汇报的经济分析仪表盘
- 提升将原始公开数据转化为结构化分析结果的能力

## 数据来源
- World Bank Open Data
- API 工具：`wbgapi`
- 时间范围：2000–2024
- 研究对象：危地马拉（GTM）
- 对照组：世界整体（WLD）、中等偏上收入国家（UMC）

## 技术栈
- Python
- wbgapi
- pandas
- matplotlib
- seaborn

## 项目方法
1. **数据抓取**  
   使用 `wbgapi` 从世界银行数据库获取危地马拉及对照组的宏观经济指标，包括实际 GDP、人均 GDP、通胀、失业率、劳动参与率、储蓄、投资、出口、进口、税收收入和政府支出等。

2. **数据清洗与整理**  
   使用 `pandas` 对 API 返回数据进行转置、索引规范化、缺失值处理和时间序列整理，构建适用于分析的 DataFrame。

3. **衍生指标构造**  
   在原始指标基础上进一步计算和构造：
   - 财政平衡代理指标：税收收入 - 政府支出
   - 贸易平衡代理指标：出口占 GDP 比重 - 进口占 GDP 比重
   - 自然失业率代理指标：失业率滚动平均
   - 生产率代理指标：实际 GDP / 总劳动力

4. **可视化分析**  
   使用 `matplotlib` 和 `seaborn` 绘制多类图表，包括折线图、柱状图、双变量对比图和 2×3 宏观经济仪表盘（Executive Dashboard），用于总结危地马拉经济表现。

## 项目亮点
- 使用 API 直接对接公开数据库，构建了可重复的数据获取流程
- 将原始宏观经济数据整理为标准化时间序列分析框架
- 不局限于单一 GDP 指标，而是从增长、就业、价格稳定、财政、外贸和资本形成等多个角度进行综合分析
- 输出了面向汇报场景的可视化 Dashboard，具备较强展示性和业务表达能力

## 核心发现
- 危地马拉在样本期内实现了经济总量增长，但相对世界和中等偏上收入国家的追赶并不明显
- 单看 GDP 增长容易高估发展成效，结合人均产出、就业和外部平衡后，可以看到更复杂的结构性问题
- 财政平衡与贸易平衡长期承压，反映出经济发展中的可持续性约束
- 储蓄与投资之间的差异提示了资本积累和融资能力方面的潜在挑战

## 项目产出
- 宏观经济数据分析 Notebook
- 多张时间序列可视化图表
- 2×3 经济概览仪表盘（Guatemala Economic Snapshot）

## 能力体现
通过本项目，我展示了以下能力：
- 使用 Python 进行公开经济数据抓取与处理
- 使用 pandas 进行时间序列清洗、整理与衍生指标构造
- 使用 matplotlib / seaborn 输出结构化可视化结果
- 从数据中提炼经济现象并形成简洁、清晰的分析结论
