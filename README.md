# ML-Optimized Neem-Tulsi Repellents For Karnataka Dengue Control

[![KSCST SPP](https://img.shields.io/badge/KSCST-SPP%20Reference%3A%2047S__MSC__0145-blue.svg)](https://www.kscst.org.in/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An AI-driven computational framework evaluating phytochemicals from **Neem (*Azadirachta indica*)** and **Tulsi (*Ocimum sanctum*)** as sustainable vector-control repellents against *Aedes aegypti* mosquito targets (**3K1E** and **60PB**).

Developed under the **47th Series of the Student Project Programme (SPP)** funded by the **Karnataka State Council for Science and Technology (KSCST)** at **Garden City University, Bengaluru**.

---

## 📌 Project Overview
Dengue fever remains a critical public health challenge in Karnataka. Synthetic insect repellents pose environmental toxicity, non-target risks, and bioaccumulation hazards. This repository integrates cheminformatics, molecular docking, molecular dynamics (MD) simulations, and machine learning to rapidly screen natural bioactive candidates from traditional Neem and Tulsi formulations.

---

## 🛠️ Key Features & Workflow
1. **Phytochemical Retrieval & Cheminformatics**: Curated ~200 bioactive compounds from *Dr. Duke's Phytochemical Database* and *IMPPAT*, computing key descriptors (MolWt, LogP, TPSA, HBD, HBA, RotBonds) via **RDKit**.
2. **Molecular Docking**: Conducted docking studies using **AutoDock Vina** against mosquito odorant-binding targets (**3K1E** and **60PB**) to map active-site interactions.
3. **Molecular Dynamics (MD) Simulations**: Ran 50 ns production simulations in **GROMACS** (AMBER force field, TIP3P solvent model) to evaluate structural stability (RMSD, RMSF, Rg, SASA).
4. **Machine Learning QSAR Regression**: Modelled binding affinities using **Random Forest** and **Gradient Boosting** algorithms with Leave-One-Out (LOO) cross-validation.

## 🧬 Key Findings & Biological Insights
* **Top-Performing Model**: Gradient Boosting outperformed Random Forest with a LOO $R^2$ of 0.8659 and lower error metrics, making it a reliable predictive framework.
* **Primary Binding Drivers**: Feature importance and correlation analysis demonstrated that molecular size multiplied by polar surface area (`MolWt_TPSA`) and total hydrogen bonding capacity (`H_total`) are the most critical factors for ligand binding efficiency.
* **Lead Phytochemical Candidate**: **Azadirachtin** consistently emerged as the strongest binder across both mosquito odorant-binding targets, exhibiting binding affinities of -11.4 kcal/mol (3K1E) and -10.6 kcal/mol (60PB).

## 📦 Project Deliverables & Generated Assets
The pipeline automatically compiles and outputs publication-ready assets into the repository:
* **High-Resolution Visualizations (300 DPI PNG)**:
  * `DT_01_predictions.png`: Actual vs. predicted model accuracy and target comparisons.
  * `DT_02_feature_importance.png`: Feature ranking comparison between Random Forest and Gradient Boosting.
  * `DT_03_target_comparison.png`: Dual-target binding analysis across 3K1E and 60PB.
* **Publication Data Tables (CSV)**[cite: 11]: Contains complete prediction errors, performance metrics, and individual feature rankings.
* **Comprehensive Summary Report**: Available in `DUAL_TARGET_SUMMARY.txt` for immediate review.

## 📊 Summary of Results

| Algorithm | Training R² | Training RMSE | Training MAE | LOO R² | LOO RMSE | LOO MAE |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Random Forest** | 0.9264 | 0.4215 | 0.3007 | 0.7381 | 0.7950 | 0.5573 |
| **Gradient Boosting** | 0.9665 | 0.2845 | 0.2438 | 0.8659 | 0.5690 | 0.4875 |

* **Key Predictor:** Feature importance and Pearson correlation analyses revealed that Molecular Weight × Polarity (MolWt_TPSA) and total hydrogen-bonding capacity (H_total) are the dominant drivers of binding affinity[cite: 17].
* **Lead Compound:** Azadirachtin consistently emerged as the strongest binder across both targets (-11.4 kcal/mol on 3K1E and -10.6 kcal/mol on 60PB).

## 🗺️ Future Scope & Roadmap
* **Expanded Compound Libraries**: Integrate additional plant-derived bioactives with recognized insecticidal properties to broaden chemical diversity.
* **Advanced Machine Learning**: Implement alternative regression algorithms such as XGBoost, Support Vector Machines (SVM), and neural networks.
* **Extended Molecular Dynamics**: Scale simulations beyond 50 ns (e.g., 100 ns+) and perform MM-PBSA free energy calculations for deeper thermodynamic insight.
* **Experimental Validation**: Transition top in-silico candidates into in vitro binding assays and physical repellency field trials.

---
