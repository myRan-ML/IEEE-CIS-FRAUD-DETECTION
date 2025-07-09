# IEEE-CIS 欺诈检测

## 项目概述

本项目是我参与 Kaggle [IEEE-CIS 欺诈检测](https://www.kaggle.com/c/ieee-fraud-detection) 竞赛的解决方案，旨在预测在线交易中的欺诈行为。该项目展示了从数据探索、模型构建到部署的完整机器学习工作流程。

## 竞赛背景：IEEE-CIS

电气与电子工程师协会 - 计算智能学会（IEEE-CIS）与业内专家合作发起此挑战，使用由领先支付服务公司 Vesta Corporation 提供的真实交易数据。

## 方法论

本 Notebook 实现了一个完整的欺诈检测流程：

### 数据探索
- 特征分布可视化
- 使用 T 检验和卡方检验评估统计相关性

### 建模方法
- 逻辑回归（Logistic Regression）
- 多层感知机（MLP）
- XGBoost
- 随机森林（Random Forest）

### 评估指标
- 主指标：AUC-ROC（接收器操作特征曲线下的面积）
- 次指标：精确率-召回率曲线（PR Curve）
- 补充指标：Top 5 和 Top 10 精确率

## 快速开始

### 环境依赖
- Python 3.7+
- Jupyter Notebook 或 Lab

### 安装步骤

```bash
git clone https://github.com/myRan-ML/IEEE-CIS-FRAUD-DETECTION.git
cd ieee-cis-fraud-detection
pip install -r requirements.txt
```

## 数据准备
- 从 Kaggle 数据页面 下载竞赛数据
- 在项目根目录下创建 data/ 文件夹
- 将所有 CSV 文件放入 data/ 文件夹中


## 运行 Notebook
```bash
jupyter notebook IEEE_CIS_Fraud_Detection.ipynb
```

## 关键洞察
### 类别不平衡问题：
- 欺诈交易仅占约 3.5%

- 使用类别权重进行补偿处理

### 特征重要性分析：

- 交易金额和交易频率是最关键的预测因子

- 某些卡类型更容易被欺诈

### 模型性能：

- 表现最佳的单模型为 XGBoost，AUC 达到 0.917

## 模型评估结果
| 模型      | 训练集 AUC  | 测试集 AUC  | 训练集 PR AUC | 测试集 PR AUC | Top 5 精确率 | Top 10 精确率 |
| ------- | -------- | -------- | ---------- | ---------- | --------- | ---------- |
| 逻辑回归    | 0.543805 | 0.504985 | 0.039877   | 0.034906   | 0.0       | 0.0        |
| 多层感知机   | 0.500011 | 0.499930 | 0.035136   | 0.034409   | 0.0       | 0.0        |
| 随机森林    | 0.879251 | 0.857202 | 0.516721   | 0.426802   | 1.0       | 1.0        |
| XGBoost | 0.980381 | 0.917417 | 0.878228   | 0.558776   | 1.0       | 1.0        |
