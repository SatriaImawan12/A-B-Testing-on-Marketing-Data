# 📊 Marketing A/B Testing Analysis

A statistical analysis project to determine whether an advertisement has a significantly higher impact on user conversion rates compared to a public service announcement (PSA), using a **Two-Sample Z-Test for Proportions**.

---

## 🎯 Objective

Compare conversion rates between two user groups:
- **AD Group** (Treatment) — users who saw the advertisement
- **PSA Group** (Control) — users who saw the public service announcement

---

## 📁 Dataset

**File:** `marketing_AB.csv`

| Column | Description |
|---|---|
| `user id` | Unique user identifier |
| `test group` | `ad` = saw advertisement, `psa` = saw public service announcement |
| `converted` | `True` if user purchased the product, `False` otherwise |
| `total ads` | Total number of ads seen by the user |
| `most ads day` | Day of the week the user saw the most ads |
| `most ads hour` | Hour of the day the user saw the most ads |

---

## 🔍 Exploratory Data Analysis

### Ad Reach by Day
| Day | Count |
|---|---|
| Friday | 92,608 |
| Monday | 87,073 |
| Sunday | 85,391 |
| Thursday | 82,982 |
| Saturday | 81,660 |
| Wednesday | 80,908 |
| Tuesday | 77,479 |

> **Insight:** Friday, Monday, and Sunday saw the highest ad reach among all days.

### Top Conversion Days
Monday, Tuesday, and Sunday were the top three days for conversions.

### Peak Ad Hours
The period between **11:00 – 15:00** is the peak time for ad viewership.

---

## 🧪 A/B Testing Methodology

**Method:** Two-Sample Z-Test for Proportions  
**Library:** `statsmodels.stats.proportion.proportions_ztest`  
**Significance Level (α):** 0.05

**Hypotheses:**
```
H₀ : There is no difference in conversion rates between the AD and PSA groups
H₁ : There is a significant difference in conversion rates between the groups
```

---

## 📈 Results

| Metric | AD Group (Treatment) | PSA Group (Control) |
|---|---|---|
| Conversion Rate | **2.55%** | 1.79% |
| Total Users | 564577 | 23524 |
| Conversions | 14423 | 420 |

| Statistical Test | Value |
|---|---|
| Z-Statistic | **7.3701** |
| P-Value | **0.0001** |
| Result | ✅ Reject H₀ |

> Since **p-value (0.0001) < α (0.05)**, we reject the null hypothesis. The advertisement had a **statistically significant positive impact** on conversion rates, achieving a **+42.5% relative lift** over the PSA group.

---

## 💡 Key Findings & Recommendations

1. **Scale the Advertisement** — The +42.5% conversion uplift is statistically validated. Full deployment to a broader audience is recommended.
2. **Target Peak Hours** — Schedule ad delivery between **11:00–15:00**, especially on **Mondays and Tuesdays** for maximum conversion.
3. **Segment & Optimize** — Analyze user characteristics within the AD group to identify high-converting segments for future targeting.

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat)
![Seaborn](https://img.shields.io/badge/Seaborn-4c72b0?style=flat)
![Statsmodels](https://img.shields.io/badge/Statsmodels-3f7f93?style=flat)

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/username/marketing-ab-testing.git
   cd marketing-ab-testing
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels
   ```

3. **Place the dataset** `marketing_AB.csv` in the root directory

4. **Run the notebook** in Google Colab or Jupyter:
   ```bash
   jupyter notebook ab_testing.ipynb
   ```

   Or open directly in Google Colab:  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1su5RN9J34vY50hOIZWb5sU2kFlUvnWxz)

---

## 📊 Report
https://699d5ea0277313333cce117b--ab-testing-marketing.netlify.app/

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
