# NEDL 金融计量学习资料

金融计量、量化投资与风险管理方面的学习资料合集：**200+ 个 Excel 模型、16 个 Python Notebook、50+ 篇经典论文**，按 NEDL 系列教程整理。

## 目录

| 文件夹 | 数量 | 内容 |
| --- | --- | --- |
| [`Excel 101/`](Excel%20101) | 14 | Excel 基础：日期 / 文本函数、VLOOKUP、INDEX、排序、矩阵运算、线性方程组、LINEST、随机数、收益率计算、散点图、直方图、STOCKHISTORY、Nelson-Siegel-Svensson |
| [`Sheets/`](Sheets) | 200+ | 专题 Excel 模型（见下表） |
| [`Python code/`](Python%20code) | 16 | Jupyter Notebook 实现 |
| [`Papers/`](Papers) | 55 | 相关经典论文 PDF |

### Sheets 专题分类

| 主题 | 示例 |
| --- | --- |
| 统计检验 | t 检验、F 检验、卡方检验、Jarque-Bera、Kolmogorov-Smirnov、Anderson-Darling、Cramér-von Mises、游程检验、多重检验 |
| 回归与计量 | 多元回归、虚拟变量、Logit / Probit、Tobit、分位数回归、Ridge / LASSO / Elastic Net、多重共线性与 VIF、异方差与 HAC、工具变量、Theil-Sen |
| 时间序列 | AR / MA、自相关、Dickey-Fuller、KPSS、协整、Hurst 指数、方差比检验、马尔科夫链、指数平滑 |
| 波动率模型 | ARCH、GARCH 及其扩展、DCC-GARCH、HAR / HARQ、OHLC 波动率（Parkinson 等） |
| 投资组合 | 有效前沿、资本市场线、Black-Litterman、风险平价、最大去相关、再平衡、高阶矩组合、Treynor-Black |
| 绩效评价 | Sharpe / 概率 Sharpe / 收缩 Sharpe、Information Ratio、Omega、Ulcer / Martin、择时能力（Henriksson-Merton） |
| 风险管理 | VaR、CVaR、VaR 回测、KMV、CreditRiskMetrics、Basel III、LCR / NSFR、操作风险 |
| 衍生品与固收 | Black-Scholes、障碍期权、蒙特卡洛定价、Heston、CIR、Vasicek、久期与凸性、Nelson-Siegel、CDS、期货套利 |
| 市场异象与行为金融 | 日历效应、一月效应、“Sell in May”、月相效应、羊群效应、季节性情绪失调（SAD）、价格聚集 |
| 估值 | DDM、股权成本、估值乘数、PEG、IRR、回收期 |

### Python Notebook

GARCH、广义误差分布、Johnson SU 分布与障碍期权定价、分布拟合、有效前沿、协整配对交易（两部分）、泡沫检测、游程检验、方差比检验、滚动 Hurst 指数，以及 Bollinger Bands / MACD / RSI / 支撑阻力等技术交易策略。

## 使用

- Excel 文件需要 **Microsoft Excel 365**（部分用到动态数组、`STOCKHISTORY`、规划求解 Solver）。
- Notebook 环境：

```bash
pip install numpy pandas scipy matplotlib yfinance statsmodels jupyter
jupyter notebook "Python code"
```

## 版权说明

本仓库为个人学习整理。Excel 模型与 Notebook 的原始版权归 NEDL 系列作者所有，`Papers/` 中的论文版权归原作者及出版方所有，请勿用于商业用途。
