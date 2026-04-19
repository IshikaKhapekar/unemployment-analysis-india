# 📊 Unemployment Pattern Analysis & Scheme Effectiveness — India

## 📌 Project Overview

This project performs a comprehensive analysis of unemployment
patterns across Indian states using real government datasets.

It combines three analytical approaches:
- Data Analysis — understanding unemployment trends across
  states, regions, time periods and rural vs urban divide
- Machine Learning — classifying states into unemployment
  risk categories using supervised learning models
- NLP — analysing employment scheme descriptions to map
  which schemes target which unemployed groups

---

## 📊 Datasets Used

| Dataset | Source | Records |
|---|---|---|
| Unemployment in India | Kaggle | 740 rows |
| Global Unemployment Rate | Kaggle / World Bank | 235 countries |
| MGNREGS District Data | Kaggle | 740 districts |

**Unemployment Dataset Features:**
| Feature | Description |
|---|---|
| State | Indian state name |
| Date | Monthly date (2019–2020) |
| Unemployment Rate | % of labour force unemployed |
| Employed | Number of employed persons |
| Labour Participation Rate | % of population in labour force |
| Area | Rural or Urban |

---

## 🔍 Key Findings from EDA

### 1. Top Unemployment States
Certain states consistently show unemployment rates
significantly above the national average across both
rural and urban areas throughout 2019 and 2020.

### 2. Rural vs Urban Divide
Urban unemployment is higher than rural unemployment
on average. This reflects the larger informal rural
workforce which is often undercounted in formal
unemployment statistics.

### 3. COVID-19 Impact
2020 shows a sharp spike in average unemployment rate
compared to 2019 across almost all states, with urban
areas hit significantly harder than rural areas during
the lockdown period.

### 4. Labour Participation Rate
States with higher labour participation rates do not
always have lower unemployment — indicating structural
issues in job creation rather than workforce availability.

### 5. Monthly Trend
Unemployment peaked sharply between April and June 2020
coinciding with the national lockdown, followed by a
gradual recovery from July 2020 onwards.

---

## 🤖 Machine Learning — Unemployment Risk Classification

### Problem Statement
Classify each state-month observation into one of three
unemployment risk categories:
- 🔴 High — Unemployment rate above 15%
- 🟠 Medium — Unemployment rate between 7% and 15%
- 🟢 Low — Unemployment rate below 7%

### Models Trained

| Model | Accuracy |
|---|---|
| Logistic Regression | 0.4257 |
| Random Forest | 0.7297 |
| XGBoost | 0.6689 |

*Best Model: Random Forest with Accuracy: 0.7297*

### Features Used
- State
- Area (Rural / Urban)
- Employed count
- Labour Participation Rate
- Month
- Year

### Key Finding
Labour Participation Rate and State are the strongest
predictors of unemployment risk category. Month is also
significant due to the COVID seasonal effect in 2020.

---

## 🗂️ K-Means Clustering — State Risk Profiling

States were clustered into 3 groups based on:
- Average Unemployment Rate
- Average Labour Participation Rate
- Average Employed Count

### Cluster Results

| Cluster | States | Characteristics |
|---|---|---|
| 🔴 High Unemployment | 'Bihar', 'Chandigarh', 'Delhi', 'Haryana', 'Himachal Pradesh', 'Jammu & Kashmir', 'Jharkhand', 'Tripura' | High rate, low participation |
| 🟠 Medium Unemployment | 'Maharashtra', 'Uttar Pradesh', 'West Bengal' | Moderate on both metrics |
| 🟢 Low Unemployment | 'Andhra Pradesh', 'Assam', 'Chhattisgarh', 'Goa', 'Gujarat', 'Karnataka', 'Kerala', 'Madhya Pradesh', 'Meghalaya', 'Odisha', 'Puducherry', 'Punjab', 'Rajasthan', 'Sikkim', 'Tamil Nadu', 'Telangana', 'Uttarakhand' | Low rate, high participation |


### What Each Cluster Means

**🔴 High Unemployment States**
These states have structurally high unemployment.
Both rural and urban joblessness is above national average.
Key issues include limited industrial base, low skill levels,
and high dependence on seasonal agricultural employment.
Actions needed:
→ Accelerate skill development programmes
→ Attract manufacturing investment
→ Strengthen rural employment guarantee coverage
→ Improve urban informal sector support

**🟠 Medium Unemployment States**
These states are stable but vulnerable.
One economic shock like a bad monsoon or industry slowdown
can push them into the high unemployment category.
Actions needed:
→ Diversify economic base
→ Improve social protection coverage
→ Monitor monthly unemployment data closely
→ Strengthen crop insurance and rural safety nets

**🟢 Low Unemployment States**
These states have strong employment ecosystems.
High labour participation and low unemployment suggest
well-functioning labour markets.
Lessons from these states:
→ Study their industrial policy for replication
→ Analyse skill training ecosystem
→ Understand rural-urban migration patterns

---

## 📝 NLP Analysis — Employment Scheme Targeting

Four major employment schemes were analysed using
Natural Language Processing to understand which
unemployed groups each scheme targets.

### Schemes Analysed
- MGNREGS — Rural wage employment guarantee
- PMKVY — Skill development for youth
- PM SVANidhi — Street vendor support
- PMEGP — Self employment through micro enterprises

### Method
- Scheme descriptions cleaned and tokenized
- Stopwords removed
- Top keywords extracted using frequency analysis
- Word clouds generated per scheme
- Target group coverage matrix built

### Key Finding
No single scheme covers all unemployed groups.
MGNREGS targets rural unskilled workers strongly but
misses urban youth. PMKVY targets youth but has weak
rural penetration. This gap analysis reveals where
scheme design can be improved to cover missing groups.

### Scheme Coverage Matrix
See `outputs/scheme_coverage_matrix.csv` and
`outputs/chart23_scheme_coverage_heatmap.png`
for the full coverage matrix across 10 target groups.

---

## 📈 MGNREGS Deep Dive

### Key Metrics Analysed
- Total expenditure by state
- Women participation percentage
- Average wage per day
- Scheme reach percentage (active workers / total workers)
- Households completing 100 days of employment

### Finding
States with higher MGNREGS expenditure do not always
show lower unemployment rates. This suggests that
expenditure alone is not enough — targeting efficiency
and wage levels matter equally.

States with high women participation in MGNREGS tend
to show lower rural unemployment among women,
suggesting the scheme is effective when women
actively participate.

---

## 🛠️ Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Core programming |
| Pandas | Data cleaning and manipulation |
| NumPy | Numerical operations |
| Matplotlib + Seaborn | Data visualisation |
| Scikit-learn | ML models and clustering |
| XGBoost | Best classification model |
| NLTK | Text tokenization and stopwords |
| WordCloud | Scheme keyword visualisation |
| Google Colab | Development environment |

---

## 🚀 How to Run

1. Open notebook in Google Colab:
   `notebooks/unemployment_analysis_india.ipynb`

2. Upload datasets from `data/` folder

3. Run all cells top to bottom

4. All charts save to `outputs/` folder

---

## 💡 Key Takeaways

- Urban unemployment is consistently higher than rural
  unemployment across all Indian states
- COVID-19 caused a sharp spike in April-June 2020
  with urban areas hit significantly harder
- No single employment scheme covers all unemployed
  groups — there are clear targeting gaps
- MGNREGS reach is high but wage levels vary widely
  across states indicating implementation gaps
- States with high labour participation do not always
  have low unemployment — structural job creation
  is the real bottleneck

---

## 📁 Author

**Ishika Khapekar**
