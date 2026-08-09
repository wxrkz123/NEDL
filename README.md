# 🔬 NEDL (Network Econometrics & Data Logistics)

欢迎来到 **NEDL** 项目仓库。本仓库致力于复杂网络分析 (CNA)、高级计量经济学模型以及大规模微观数据集的清洗与计算。项目整合了 Python 高效的数据管道与 Stata 严谨的计量分析，旨在为物流运输、空间经济学及政策评估等研究提供可靠的代码实现。

## 🎯 项目核心模块

本项目主要涵盖以下三大研究维度的代码实现：

1. **大规模数据处理**：利用 Pandas 和 DuckDB 处理超大型数据集（支持 200GB+ 数据量的内存优化），包含精细化的数据清洗与分类映射。
2. **高级因果推断**：包含工具变量 (Bartik IV, 2SLS)、空间计量 (Spatial Econometrics) 以及结合了 DID 交互项的双重机器学习 (DDML) 模型。
3. **复杂网络分析 (CNA)**：构建基于引力模型的航运/物流网络，计算节点度中心性 (Degree Centrality)，评估枢纽辐射网络 (Hub-and-spoke) 的韧性与连通性指数。

## 📂 目录结构 (Directory Structure)

```text
NEDL/
├── 01_Data_Pipeline/         # 大规模数据处理脚本
│   ├── duckdb_queries/       # 高效 SQL 查询与聚合
│   └── cleaning_scripts/     # 数据清洗 (注: 包含精准的分类映射字典，如 4_No_SW 等，不使用模糊的 fallback 默认值)
├── 02_Econometrics_Models/   # 计量经济学估计模型
│   ├── DDML/                 # 双重机器学习 (注: 框架内嵌入 DID 交互项的特定实现)
│   ├── IV_2SLS/              # 工具变量法与两阶段最小二乘法
│   └── Spatial_Models/       # 空间计量模型 (基于 Stata xsmle 等命令)
├── 03_Network_Analysis/      # 复杂网络构建与指标计算
│   ├── gravity_models/       # 引力模型测算
│   └── resilience_metrics/   # 网络韧性与连通性分析
├── 04_Visualizations/        # 学术级多指标可视化
│   └── core_metrics/         # 核心变量绘图 (如：Expenditure, Birth Rate, Carbon Emissions 等)
└── docs/                     # 参考文献与推导笔记

```

## 💻 环境依赖与配置 (Installation)

### Python 环境

推荐使用 Anaconda 管理虚拟环境。核心依赖包如下：

* `pandas`, `numpy` (基础数据处理)
* `duckdb` (超大规模数据集的本地查询与计算)
* `networkx` (复杂网络构建)
* `EconML` / `DoubleML` (机器学习因果推断)
* `tensorflow` (深度学习模块)

### Stata 环境

运行本仓库的 `.do` 文件需要安装以下核心外部命令：

```stata
ssc install reghdfe
ssc install ftools
ssc install ivregress
ssc install xsmle

```

## ⚠️ 研究与代码规范建议 (Best Practices)

在复现或扩展本仓库的代码时，请注意以下研究规范：

1. **分类映射严谨性**：在处理航线、航站楼或港口等离散类别数据时，必须在代码中显式列出所有映射字典（Explicit Mapping），避免依赖默认的 fallback 分类，以防数据遗漏。
2. **反向因果检验的逻辑约束**：在进行反向因果测试解释时，由于不同变量的量纲和标度不同，**严禁直接比较回归系数的绝对值大小**，应侧重于系数的显著性与经济学直觉。
3. **绘图指标精简**：为了保证图表的学术严谨性和信息聚焦，可视化脚本默认排除了不必要的中介变量（如 Disposable_Income），专注于核心自变量与因变量（如支出、生育率与碳排放）的多维关系呈现。

## 🤝 合作与贡献 (Contributing)

本仓库为学术研究型项目。在提交 Pull Request 之前，请确保您的代码已通过自测，并符合目标顶级期刊（如 *TRE*, *JTG* 等）的稳健性要求。如有模型逻辑疑问，请通过 Issue 提出。

## 📄 许可证 (License)

本项目采用 [MIT License](https://www.google.com/search?q=LICENSE) 开源许可证。可以自由用于学术交流与二次开发，引用时请注明出处。
