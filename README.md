# test1
航空发动机故障风险预测：融合热力学机理与机器学习的跨学科实践
Aero-Engine Fault Risk Prediction: A Physics-Driven Machine Learning Approach

📌 项目简介 (Project Overview)
本项目旨在解决航空发动机运维中“视情维修（CBM）”的痛点 。
航空发动机维修成本占飞机总运维成本的 30%-40%，准确的故障预警对保障飞行安全及优化经济效益至关重要 。
本项目通过将剩余寿命（RUL）预测转化为二分类风险预警任务（阈值设置为 21 周期），利用 XGBoost 模型实现了对发动机失效风险的高精度感知 。

🌟 核心亮点 (Key Highlights)
物理机理引导的特征工程 (Physics-Driven Feature Engineering)：不同于纯数据驱动方法，本项目参考**布雷顿循环（Brayton Cycle）原理，构造了高压压气机压比（$P30/P2$）**和温比特征 。
抵消工况波动 (Normalization Effect)：通过比率特征有效抵消了复杂工况带来的传感器数据噪声，相比原始特征使 $ROC-AUC$ 提升了约 0.08 。
解决极度不平衡数据 (Handling Data Imbalance)：针对故障样本不足 10% 的行业常态，采用 SMOTE 过采样策略优化了模型对少数类故障的识别能力 。
模型可解释性 (Explainability)：引入 SHAP 框架，从物理底层逻辑验证了性能衰退与核心部件磨损的演化过程 。

🛠️ 技术栈 (Tech Stack)
语言：Python 3.x核心库：Scikit-learn, XGBoost, Pandas, NumPy优化与评估：贝叶斯优化（Bayesian Optimization）, 5 折交叉验证, 阈值搜索 可解释性工具：SHAP (SHapley Additive exPlanations)

📊 实验结果 (Results)
模型在验证集上取得了卓越的分类性能：ROC-AUC：$\approx 0.996$ F1-Score：$\approx 0.913$ 通过 SHAP 分析识别出运行周期数（Cycle）、修正风扇转速、涵道比和**高压压气机出口静压（P30）**为故障预测的关键诱因 。
