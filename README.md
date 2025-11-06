# Drug Safety Hypothesis Testing 💊📊

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Complete-success.svg)]()

A comprehensive statistical analysis of pharmaceutical drug safety data to evaluate adverse effects between treatment and placebo groups.

## 🎯 Project Overview

This project analyzes clinical trial data from **GlobalXYZ Pharmaceuticals** to assess drug safety through rigorous hypothesis testing. As a non-profit organization focused on drug safety, we evaluate whether adverse reactions differ significantly between drug and placebo groups, ensuring transparency and reproducibility in pharmaceutical research.

### Key Questions Investigated

1. **Do adverse effect proportions differ between Drug and Placebo groups?**
2. **Is the number of adverse effects independent of treatment assignment?**
3. **Are there demographic differences (age) between treatment groups?**

## 📁 Repository Structure

```
Drug-Safety-Hypothesis-Testing/
│
├── data/
│   ├── drug_safety.csv                    # Original clinical trial dataset
│   ├── input_data_drug_safety.json        # Processed data in JSON format
│   └── statistical_test_results.csv        # Summary of all statistical tests
│
├── Hypothesis Testing.ipynb                # Main analysis notebook
├── index.html                              # Project web interface
└── README.md                               # Project documentation
```

## 📊 Dataset Description

**Source:** Vanderbilt University Department of Biostatistics ([Hbiostat](http://hbiostat.org/data))

**Study Design:** Randomized controlled trial with 2:1 drug-to-placebo ratio

### Dataset Specifications

- **Total Participants:** 16,103
- **Treatment Groups:** 
  - Drug: 10,727 participants (66.6%)
  - Placebo: 5,376 participants (33.4%)
- **Time Period:** 20-week follow-up
- **Demographics:** Ages 39-84 years, 76.6% male, 23.4% female

### Variables

| Column | Description |
|--------|-------------|
| `sex` | Gender of participant (male/female) |
| `age` | Age in years (39-84) |
| `week` | Week of drug testing (0-20) |
| `trx` | Treatment assignment (Drug/Placebo) |
| `wbc` | White blood cell count |
| `rbc` | Red blood cell count |
| `adverse_effects` | Presence of adverse effects (Yes/No) |
| `num_effects` | Number of adverse effects (0-3) |

## 🔬 Methodology

### Statistical Tests Performed

#### 1. Two-Sample Proportion Test (Z-test)
- **Null Hypothesis (H₀):** Proportions of adverse effects are equal between groups
- **Alternative Hypothesis (H₁):** Proportions differ between groups
- **Test Statistic:** Z = 0.0452
- **P-value:** 0.9639
- **Conclusion:** ✅ No significant difference in adverse effect rates

#### 2. Chi-Square Test of Independence
- **Null Hypothesis (H₀):** Number of adverse effects is independent of treatment
- **Alternative Hypothesis (H₁):** Number of adverse effects depends on treatment
- **Test Statistic:** χ² = 1.7996 (df = 3)
- **P-value:** 0.6150
- **Conclusion:** ✅ Number of adverse effects is independent of treatment group

#### 3. Mann-Whitney U Test (Age Comparison)
- **Null Hypothesis (H₀):** Age distributions are equal between groups
- **Alternative Hypothesis (H₁):** Age distributions differ between groups
- **Test Statistic:** U = 29,149,339.5
- **P-value:** 0.2570
- **Conclusion:** ✅ No significant age difference between treatment groups

### Significance Level
All tests conducted at **α = 0.05** (95% confidence level)

## 📈 Key Findings

### Adverse Effects Profile

| Group | Adverse Effects Rate | Mean Age | Sample Size |
|-------|---------------------|----------|-------------|
| **Drug** | 9.55% | 64.19 ± 8.73 years | 10,727 |
| **Placebo** | 9.52% | 63.97 ± 8.89 years | 5,376 |
| **Difference** | +0.03% | +0.22 years | - |

### Statistical Results Summary

| Test | P-Value | Significance | Effect Size |
|------|---------|--------------|-------------|
| Proportion Test | 0.9639 | Not Significant | Cohen's h = 0.0008 |
| Chi-Square | 0.6150 | Not Significant | Cramér's V = 0.0106 |
| Mann-Whitney U | 0.2570 | Not Significant | r = -0.0109 |

### Clinical Implications

✅ **Positive Findings:**
- Drug shows **no significant increase** in adverse effects compared to placebo
- Treatment groups are **well-balanced** demographically
- Study demonstrates **robust randomization** (exact 2:1 ratio achieved)
- Low overall adverse event rate (9.5%) indicates good safety profile

⚠️ **Considerations:**
- 43% missing data in lab values (WBC/RBC) - future analyses should investigate
- Most adverse effects are mild (89% experience ≤1 effect)
- Effect sizes are negligible across all comparisons

## 🛠️ Technical Implementation

### Dependencies

```python
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scipy>=1.7.0
statsmodels>=0.13.0
```

### Installation

```bash
# Clone the repository
git clone https://github.com/BigTime5/Drug-Safety-Hypothesis-Testing.git
cd Drug-Safety-Hypothesis-Testing

# Install required packages
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook "Hypothesis Testing.ipynb"
```

### Running the Analysis

```python
# Load the dataset
import pandas as pd
df = pd.read_csv('data/drug_safety.csv')

# The notebook executes three main analyses:
# 1. Exploratory Data Analysis (EDA)
# 2. Statistical Hypothesis Testing
# 3. Visualization and Reporting
```

## 📊 Visualizations

The analysis includes professional visualizations:

- **Adverse Effects Distribution:** Bar charts comparing Drug vs Placebo
- **Age Distribution:** Box plots and KDE curves for demographic analysis
- **Contingency Tables:** Heatmaps showing effect counts by treatment
- **Statistical Summaries:** Comprehensive tables of all test results

## 🎓 Statistical Rigor

### Quality Assurance Measures

- ✅ Assumption checking (normality tests, equal variance tests)
- ✅ Multiple test perspective (parametric and non-parametric)
- ✅ Effect size calculations (clinical significance beyond p-values)
- ✅ Confidence interval reporting
- ✅ Complete documentation of methodology

### Reproducibility

All analyses are fully reproducible with:
- Fixed random seeds where applicable
- Complete code documentation
- Data versioning (JSON export included)
- Detailed statistical reporting

## 💡 Conclusions

### Research Questions Answered

1. ✅ **Q1:** Adverse effect proportions **DO NOT** differ significantly (p = 0.964)
2. ✅ **Q2:** Number of adverse effects **IS** independent of treatment (p = 0.615)
3. ✅ **Q3:** Age distributions **ARE** comparable between groups (p = 0.257)

### Final Verdict

**The drug demonstrates a safety profile that is statistically indistinguishable from placebo.** All null hypotheses are retained, indicating:

- No evidence of increased adverse reaction risk
- Well-balanced and properly randomized study design
- Reliable safety data for regulatory consideration

## 📚 References

- **Dataset Source:** Vanderbilt University Department of Biostatistics
- **Original Data:** [Hbiostat Drug Safety Dataset](http://hbiostat.org/data)
- **Statistical Methods:** 
  - Agresti, A. (2018). *Statistical Methods for the Social Sciences*
  - Kirkwood, B. R., & Sterne, J. A. (2003). *Essential Medical Statistics*

## 👥 Contributors

- **Primary Analyst:** [BigTime5](https://github.com/BigTime5)
- **Organization:** Non-profit Drug Safety Research Group

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- **GitHub Repository:** [Drug-Safety-Hypothesis-Testing](https://github.com/BigTime5/Drug-Safety-Hypothesis-Testing)
- **Project Website:** [index.html](https://bigtime5.github.io/Drug-Safety-Hypothesis-Testing/)
- **Dataset Source:** [Vanderbilt Biostatistics](http://hbiostat.org/data)

## 📧 Contact

For questions, suggestions, or collaboration opportunities:
- **GitHub Issues:** [Create an issue](https://github.com/BigTime5/Drug-Safety-Hypothesis-Testing/issues)
- **Repository:** [BigTime5/Drug-Safety-Hypothesis-Testing](https://github.com/BigTime5/Drug-Safety-Hypothesis-Testing)

---

<div align="center">

**⭐ If you found this analysis helpful, please consider giving it a star!**

Made with 💙 for evidence-based drug safety research

</div>
