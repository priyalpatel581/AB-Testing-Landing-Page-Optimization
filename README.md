# E-news Express A/B Testing Project

## 📊 Project Overview
This project analyzes an A/B test conducted by **E-news Express** to evaluate whether a new landing page improves user engagement and subscription rates compared to the old landing page.

## 🎯 Business Objective
E-news Express aims to understand if the new landing page design:

- Increases **time spent on the page**
- Improves **conversion (subscription) rates**
- Performs differently across **language preferences**

## 📁 Dataset
- **Source:** `abtest.csv`  
- **Size:** 100 observations  
- **Features:**
  - `user_id`: Unique identifier for each user
  - `group`: Control (old page) or Treatment (new page)
  - `landing_page`: Version shown (`old` / `new`)
  - `time_spent_on_the_page`: Minutes spent on page
  - `converted`: Subscription status (`yes` / `no`)
  - `language_preferred`: User's preferred language (English / French / Spanish)

## 🔍 Key Research Questions
1. Do users spend more time on the new landing page than the old one?  
2. Is the conversion rate higher for the new page compared to the old page?  
3. Does conversion depend on the user's preferred language?  
4. Is the mean time spent on the new page the same across different languages?

## 📈 Methodology

### Exploratory Data Analysis (EDA)
- Distribution analysis of time spent on page
- Conversion rate analysis
- Language preference distribution
- Bivariate analysis across different dimensions

### Statistical Tests Performed
- **Welch's t-test (one-tailed)** — Comparing time spent between old and new pages  
- **Two-proportion z-test** — Comparing conversion rates  
- **Chi-square test of independence** — Testing relationship between language and conversion  
- **One-way ANOVA** — Comparing mean time across language groups

## 🔬 Key Findings

### 1. Time Spent on Page
- **Result:** Users spend significantly more time on the **new page** (median ≈ 6 minutes) vs **old page** (median ≈ 4 minutes)  
- **Statistical Evidence:** t-statistic = 3.79, p-value = 0.00014  
- **Conclusion:** ✅ Reject H₀ — Strong evidence that the new page increases engagement

### 2. Conversion Rate
- **Result:** New page shows a higher conversion rate than the old page  
- **Statistical Evidence:** z-statistic = 2.41, p-value = 0.008  
- **Conclusion:** ✅ Reject H₀ — Strong evidence that the new page improves conversions

### 3. Language vs Conversion
- **Result:** Conversion appears independent of language preference  
- **Statistical Evidence:** Chi² = 3.09, p-value = 0.213  
- **Conclusion:** ❌ Fail to reject H₀ — No significant relationship found

### 4. Time Across Languages (New Page)
- **Result:** Mean time spent is similar across all language groups  
- **Statistical Evidence:** F-statistic = 0.854, p-value = 0.432  
- **Conclusion:** ❌ Fail to reject H₀ — No significant difference across languages

#### Performance by Language (summary)
- 🥇 **English speakers:** Best conversion performance  
- 🥈 **Spanish speakers:** Moderate, balanced conversion  
- 🥉 **French speakers:** Weakest conversion performance

## 💡 Recommendations
1. **Adopt the new landing page** — Implement the new design for all users as it significantly improves engagement and conversions.  
2. **Optimize early engagement**
   - Improve the first 2 minutes experience
   - Enhance headlines and calls-to-action
   - Add compelling visual elements
3. **Focus on French-speaking users**
   - Conduct qualitative research (usability testing, surveys)
   - Identify and address specific barriers to conversion
   - Consider language-specific optimizations
4. **Maintain uniform design** — Since language doesn't significantly impact performance, avoid unnecessary customization across languages.  
5. **Continue A/B testing** — Explore further experiments on:
   - Device type (mobile vs desktop)
   - Traffic source / referral channels
   - Personalized content recommendations
6. **Monitor key metrics**
   - Conversion rate trends
   - Time spent on page
   - User drop-off points
   - Language-specific performance

## 🛠️ Technologies Used
- **Python 3.x**
- Libraries:
  - `pandas` — Data manipulation
  - `numpy` — Numerical operations
  - `matplotlib` — Data visualization
  - `seaborn` — Statistical visualizations
  - `scipy.stats` — Statistical testing
  - `statsmodels` — Proportion tests

## 📊 Visualizations Included
- Distribution of time spent on page
- Conversion rate distribution
- Language preference breakdown
- Time comparison by landing page type
- Conversion rates by page type
- Conversion vs language analysis
- Time by language (new page only)

## 🚀 Getting Started

### Prerequisites
Install required Python libraries:
```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels
```

### Running the Analysis
1. Clone the repository:
   ```bash
   git clone https://github.com/priyalpatel581/AB-Testing-Landing-Page-Optimization.git
   ```
2. Ensure `abtest.csv` is in the project directory.  
3. Open `Enews_ABTest.ipynb` in Jupyter Notebook and run all cells sequentially.

## 📝 Project Structure
```
├── Enews_ABTest.ipynb    # Main analysis notebook
├── abtest.csv            # Dataset
└── README.md             # Project documentation
```

## 📌 Statistical Significance Level
All tests use **α = 0.05** (95% confidence level)

## 👥 Use Cases
- Digital marketing teams evaluating landing page designs  
- Product managers making data-driven decisions  
- UX designers testing user engagement improvements  
- Data analysts performing A/B test analysis
```
