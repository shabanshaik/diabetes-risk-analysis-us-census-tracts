# Analyzing Diabetes Risk Patterns Across U.S. Census Tracts

A comprehensive machine learning analysis using CDC PLACES data to identify behavioral risk factors and geographic patterns in diabetes prevalence across 68,172 U.S. census tracts.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)
![pandas](https://img.shields.io/badge/pandas-1.3+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📋 Project Overview

This project analyzes the relationship between modifiable behavioral risk factors and diabetes prevalence at the census tract level. Using machine learning techniques, we identified physical inactivity as the dominant predictor (76.6% feature importance) and established a critical threshold of ~20% physical inactivity as a tipping point for diabetes risk.

### Key Findings

- **Random Forest model achieved R² = 0.8728** explaining 87.3% of variance in diabetes prevalence
- **Physical inactivity** emerged as the strongest predictor with 76.6% feature importance
- **39% of U.S. census tracts** fall into the High-Risk category (11.5% diabetes prevalence)
- **Critical threshold identified**: Communities below 20% physical inactivity maintain diabetes rates under 10%
- Geographic clustering reveals a "Diabetes Belt" in Southern states (Mississippi: 14.4%, vs Colorado: 7.1%)

## 🔬 Research Questions

1. What are the relationships between lifestyle determinants and diabetes prevalence rates?
2. Can machine learning models accurately predict diabetes prevalence using behavioral factors?
3. Which states and counties experience the highest diabetes prevalence?
4. Can areas with similar health patterns be grouped to enable targeted interventions?

## 📊 Dataset

**Source:** [CDC PLACES: Local Data for Better Health, Census Tract Data 2023](https://catalog.data.gov/dataset/places-local-data-for-better-health-census-tract-data-2023-release)

| Variable | Mean | Std Dev | Correlation with Diabetes |
|----------|------|---------|---------------------------|
| Diabetes Prevalence | 10.9% | 3.7 | 1.00 |
| Physical Inactivity | 23.1% | 7.2 | 0.86 |
| Current Smoking | 16.8% | 5.9 | 0.73 |
| Sleep <7 Hours | 33.4% | 5.4 | 0.70 |
| Binge Drinking | 15.9% | 4.3 | -0.70 |

**Coverage:** 68,172 census tracts across 50 states + D.C.

## 🛠️ Methodology

### Machine Learning Models

| Model | R² | RMSE | MAE |
|-------|-----|------|-----|
| **Random Forest** | **0.8728** | **1.326** | **0.962** |
| Gradient Boosting | 0.8688 | 1.347 | 0.992 |
| Decision Tree | 0.8528 | 1.426 | 1.027 |
| Linear Regression | 0.8314 | 1.527 | 1.123 |

### Clustering Analysis

K-means clustering (k=4) identified four distinct community risk profiles:

| Cluster | Tracts | Diabetes | Physical Inactivity |
|---------|--------|----------|---------------------|
| Very High Risk | 10,717 (15.7%) | 16.8% | 38.2% |
| High Risk | 26,607 (39.0%) | 11.5% | 27.7% |
| Moderate Risk | 17,863 (26.2%) | 9.2% | 18.8% |
| Low Risk | 12,985 (19.0%) | 7.3% | 18.1% |

## 📁 Project Structure

```
diabetes-risk-analysis/
├── data/
│   ├── raw/                    # Original CDC PLACES data
│   └── processed/              # Cleaned and transformed data
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_eda_visualization.ipynb
│   ├── 03_predictive_modeling.ipynb
│   └── 04_clustering_analysis.ipynb
├── src/
│   ├── data_preprocessing.py
│   ├── model_training.py
│   ├── clustering.py
│   └── visualization.py
├── reports/
│   ├── figures/               # Generated visualizations
│   └── Final_Project_Report.pdf
├── requirements.txt
├── README.md
└── LICENSE
```

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.8+
pandas >= 1.3.0
numpy >= 1.21.0
scikit-learn >= 1.0.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
```

### Installation

```bash
# Clone the repository
git clone https://github.com/shabanshaik/diabetes-risk-analysis.git
cd diabetes-risk-analysis

# Install dependencies
pip install -r requirements.txt
```

### Running the Analysis

```bash
# Run data preprocessing
python src/data_preprocessing.py

# Run predictive modeling
python src/model_training.py

# Run clustering analysis
python src/clustering.py
```

## 📈 Visualizations

### Correlation Heatmap
![Correlation Heatmap](reports/figures/correlation_heatmap.png)

### Feature Importance
![Feature Importance](reports/figures/feature_importance.png)

### Risk Cluster Profiles
![Cluster Profiles](reports/figures/cluster_profiles.png)

## 💡 Key Implications

1. **Primary Intervention Target**: Physical activity programs should be prioritized over multi-factor approaches
2. **Population-Level Impact**: Focus on the 26,607 High-Risk tracts (39% of all tracts) for maximum reach
3. **Critical Threshold**: Reducing community physical inactivity below 20% may yield significant diabetes prevention benefits
4. **Regional Focus**: Federal resources should target the "Diabetes Belt" states (Mississippi, Alabama, Louisiana)

## ⚠️ Limitations

- Cross-sectional design prevents causal inference
- PLACES dataset lacks demographic variables (age, race, income)
- Ecological fallacy: tract-level findings may not apply to individuals
- Self-reported behavioral data may be subject to bias

## 🔮 Future Directions

- Longitudinal studies to validate the 20% physical inactivity threshold
- Integration with demographic data from American Community Survey
- Natural experiments evaluating built environment changes
- Community-randomized trials testing cluster-based interventions

## 👥 Authors

- **Shabana Shaik** - [GitHub](https://github.com/shabanshaik) | [LinkedIn](https://linkedin.com/in/shabanashaik)
- **Vishnu Vardhan Reddy Golamari**

**Advisor:** Dr. Denise Philpot, University of North Texas

## 📚 References

Key references from the analysis:

- Hu, M., et al. (2025). Diabetes prevalence and management patterns in US adults, 2001-2023
- Yang, W., et al. (2024). Different levels of physical activity and risk of developing type 2 diabetes
- Wittman, J. T., et al. (2024). Identifying priority geographic locations for Diabetes Self-Management Education
- Benavidez, G. A., et al. (2024). Chronic disease prevalence in the US: Sociodemographic and geographic variations

See [REFERENCES.md](REFERENCES.md) for complete citation list.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- CDC for providing the PLACES dataset
- University of North Texas, Department of Information Science
- ADTA 5940 Analytics Capstone Experience program

---

*This project was completed as part of the MS in Advanced Data Analytics capstone requirement at the University of North Texas, Fall 2025.*
