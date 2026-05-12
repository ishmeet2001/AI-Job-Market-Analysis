# AI Job Market Insights: Salary, Automation Risk, and Skill Demand Analysis

Data analytics and business intelligence project analyzing 500 AI job market postings to uncover how salary, automation risk, AI adoption, skills, company size, and location shape career opportunities in the AI-driven labor market.

## Project Overview

This project delivers an end-to-end analysis of AI job market dynamics using Python, SQL, Excel, and Tableau. The goal is to translate raw job posting data into business-ready insights for job seekers, analysts, educators, and hiring teams.

By analyzing role titles, industries, salaries, automation risk, AI adoption levels, company size, geography, remote-friendliness, required skills, and projected job growth, the project answers practical labor-market questions:

- Which industries pay the highest salaries?
- Which jobs face the greatest automation risk?
- Does higher AI adoption always translate into higher pay?
- Which skills appear most often across AI-related job postings?
- Which locations offer stronger salary opportunities?
- How do company size and automation exposure interact?

Using Python for cleaning, feature engineering, SQL automation, chart generation, and Excel reporting, combined with Tableau for interactive dashboarding, this project demonstrates a complete analytics workflow from raw dataset to stakeholder-ready insights.

## Key Findings

- Finance, Entertainment, and Education show the highest average salaries, each above $93K.
- High automation-risk roles have the highest average salary at $93.9K, suggesting that higher-risk work may still command strong compensation when specialized skills are required.
- Low AI-adoption companies show the highest average salary in this dataset, indicating that AI adoption level alone does not explain compensation.
- Python and Project Management are tied as the most frequent required skills, each appearing 60 times.
- New York, Singapore, Berlin, and Tokyo lead the salary ranking by location.
- Company size is evenly distributed, with small companies slightly more represented than large and medium companies.
- Remote-friendly jobs are nearly balanced with non-remote jobs, showing that flexibility is present but not dominant.

**Takeaway:** The AI job market is not simply a story of "more AI equals more pay." The strongest opportunities appear where salary, skill demand, risk exposure, industry context, and location are analyzed together.

## Skills Demonstrated

- Data cleaning, validation, profiling, and categorical standardization.
- Feature engineering for salary bands, risk/adoption combinations, and country mapping.
- SQL-based business analysis using SQLite.
- Python visualization with Plotly.
- Excel reporting with formatted multi-sheet workbooks.
- Tableau dashboard creation for interactive business intelligence.
- Translating technical outputs into career and business recommendations.

## Table of Contents

- [Objectives](#objectives)
- [Tools & Technologies](#tools--technologies)
- [Dataset Overview](#dataset-overview)
- [Data Preprocessing & Feature Engineering](#data-preprocessing--feature-engineering)
- [Post-Processing Dataset Overview](#post-processing-dataset-overview)
- [Analysis Workflow](#analysis-workflow)
- [SQL Analysis](#sql-analysis)
- [Python Visualizations](#python-visualizations)
- [Excel Reporting](#excel-reporting)
- [Tableau Dashboard](#tableau-dashboard)
- [Outcome & Insights](#outcome--insights)
- [Business Impact](#business-impact)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [Future Work & Applications](#future-work--applications)

## Objectives

**Identify Salary Drivers**

Compare average salaries across industries, locations, AI adoption levels, automation risk categories, and company sizes.

**Analyze Automation Risk**

Understand whether high automation-risk jobs are lower-value roles or specialized roles that still pay competitively.

**Evaluate AI Adoption Effects**

Test whether companies with higher AI adoption offer better compensation than low- or medium-adoption companies.

**Surface Skill Demand**

Identify the most frequently requested skills across AI-related job postings.

**Support Career Strategy**

Translate analytics outputs into practical recommendations for job seekers and analysts entering the AI labor market.

**Demonstrate End-to-End Analytics**

Build a complete portfolio solution using Python, SQLite, Plotly, Excel, and Tableau.

## Tools & Technologies

| Tool | Purpose |
| --- | --- |
| Python | Data cleaning, feature engineering, automated analysis, and visualization |
| pandas | Dataset loading, profiling, transformation, grouping, and export |
| SQLite | Structured querying and repeatable analytical outputs |
| Plotly | Professional charts exported as PNG files |
| Excel / openpyxl | Multi-sheet stakeholder report with formatting |
| Tableau | Interactive BI dashboard for exploration and presentation |
| Jupyter Notebook | Narrative analysis and executive-style insights |

These tools support a full analytics pipeline from raw CSV ingestion to dashboard-ready outputs.

## Dataset Overview

- **Source:** `ai_job_market_insights.csv`
- **Records:** 500 job postings
- **Raw Features:** 10 columns
- **Cleaned Features:** 13 columns
- **Coverage:** Global job locations including New York, Singapore, Berlin, Tokyo, Paris, Sydney, San Francisco, Toronto, London, and Dubai.

The dataset captures AI job market attributes across role, industry, company, geography, compensation, risk, skills, and growth outlook.

### Raw Dataset Columns

| Column | Description |
| --- | --- |
| Job_Title | Role title, such as Data Scientist or Cybersecurity Analyst |
| Industry | Industry category for the job posting |
| Company_Size | Small, Medium, or Large employer classification |
| Location | City or market where the role is based |
| AI_Adoption_Level | Company's AI adoption level |
| Automation_Risk | Estimated risk of automation exposure |
| Required_Skills | Primary skill associated with the job posting |
| Salary_USD | Annual salary in USD |
| Remote_Friendly | Whether the role supports remote work |
| Job_Growth_Projection | Growth, Stable, or Decline outlook |

## Data Preprocessing & Feature Engineering

Before analysis, the raw dataset was cleaned and standardized to improve consistency and make the outputs suitable for SQL querying, visualization, and reporting.

### Key Preprocessing Steps

**Duplicate Handling**

Duplicate rows were removed to avoid overcounting job categories, salaries, or skills.

```python
df = df.drop_duplicates()
```

**Categorical Standardization**

Text fields were converted to title case and stripped of extra whitespace so categories could group correctly in SQL and visualizations.

```python
for col in cat_cols:
    df[col] = df[col].astype(str).str.title().str.strip()
```

**Missing Value Validation**

The raw dataset was profiled for null values. No missing values were found across the 500 records, but a fallback fill step was included for pipeline robustness.

```python
df = df.fillna('Unknown')
```

**Salary Band Feature**

Salary values were grouped into quartile-style bands: Low, Mid, High, and Very High. This helps compare compensation levels without relying only on exact salary values.

**Risk and Adoption Combination Feature**

Automation risk and AI adoption level were combined into a single field, enabling segmentation such as `High_Medium` or `Low_High`.

**Country Mapping**

Location values were mapped to country labels to support geographic analysis and dashboard filtering.

## Post-Processing Dataset Overview

After preprocessing, the cleaned dataset contained 500 rows and 13 columns.

### Core Job Attributes

- Job title
- Industry
- Company size
- Location
- Country
- Remote-friendly status
- Job growth projection

### Market and Risk Attributes

- AI adoption level
- Automation risk
- Risk/adoption combination

### Compensation and Skill Attributes

- Salary in USD
- Salary band
- Required skill

### Dataset Balance

| Dimension | Key Distribution |
| --- | --- |
| Company Size | Small: 171, Large: 166, Medium: 163 |
| AI Adoption Level | Medium: 179, Low: 174, High: 147 |
| Automation Risk | Medium: 173, High: 169, Low: 158 |
| Remote Friendly | Yes: 251, No: 249 |
| Job Growth Projection | Growth: 169, Decline: 169, Stable: 162 |
| Salary Bands | Low, Mid, High, and Very High each contain 125 records |

This structure creates a balanced foundation for comparing market segments without one category overwhelming the analysis.

## Analysis Workflow

The project follows a repeatable five-step workflow:

1. Load, profile, clean, and standardize the raw CSV dataset.
2. Export the cleaned dataset to `ai_jobs_cleaned.csv`.
3. Load cleaned data into SQLite and run analytical SQL queries.
4. Generate charts using Plotly and export them to the `charts/` folder.
5. Build a formatted Excel workbook and connect outputs to Tableau dashboarding.

Core pipeline file:

```bash
python ai_job_market_analysis.py
```

## SQL Analysis

SQLite was used to create a structured analytical layer from the cleaned dataset. The pipeline executes 8 repeatable SQL queries and exports each result to CSV.

### SQL Outputs

| Output | Business Question |
| --- | --- |
| `1_avg_salary_by_industry.csv` | Which industries pay the most? |
| `2_job_count_and_salary_by_risk.csv` | How are job count and salary distributed by automation risk? |
| `3_top_10_required_skills.csv` | Which skills appear most frequently? |
| `4_avg_salary_by_adoption.csv` | Does AI adoption level correlate with salary? |
| `5_company_size_distribution.csv` | What company sizes dominate the dataset? |
| `6_avg_salary_by_location_top10.csv` | Which locations offer the highest average salaries? |
| `7_automation_risk_by_industry.csv` | Which industries carry higher automation risk exposure? |
| `8_top_10_job_titles.csv` | Which job titles appear most often? |

### Example Query

```sql
SELECT Industry, ROUND(AVG(Salary_USD), 2) AS Avg_Salary
FROM ai_jobs
GROUP BY Industry
ORDER BY Avg_Salary DESC;
```

## Python Visualizations

Seven Plotly charts were generated to support visual storytelling and dashboard validation.

| Chart | Purpose |
| --- | --- |
| `1_avg_salary_industry.png` | Compares average salary across industries |
| `2_automation_risk_donut.png` | Shows distribution of automation risk categories |
| `3_adoption_vs_salary.png` | Compares average salary by AI adoption level |
| `4_top_10_skills.png` | Shows most common required skills |
| `5_salary_distribution_risk.png` | Compares salary spread by automation risk |
| `6_company_size_risk_stacked.png` | Shows automation risk composition by company size |
| `7_avg_salary_location.png` | Ranks top salary locations |

These visuals help communicate insights quickly for both technical and non-technical audiences.

## Excel Reporting

The project generates `ai_jobs_summary.xlsx`, a formatted workbook designed for stakeholder review.

### Workbook Sheets

| Sheet | Description |
| --- | --- |
| Cleaned_Data | Full cleaned dataset for audit and validation |
| Industry_Summary | Job count, average salary, and high-risk percentage by industry |
| Top_10_Skills | Most frequent required skills |

Excel formatting includes bold headers, shaded header rows, adjusted column widths, and salary formatting.

## Tableau Dashboard

The Tableau workbook `AI Job Market Insight.twbx` provides an interactive BI layer for exploring the job market dataset.

**Live Dashboard:** [![Tableau](https://img.shields.io/badge/Tableau-Dashboard-blue?logo=tableau)](https://public.tableau.com/app/profile/ish.kaur2264/viz/AIjobmarket_17770748730240/Dashboard1)

### Dashboard Features

- Salary comparison by industry and location.
- Automation risk distribution.
- AI adoption and salary comparison.
- Skill frequency exploration.
- Company size and automation risk segmentation.
- Filters for slicing the dataset by key dimensions.

The dashboard is intended for portfolio presentation and stakeholder-style analysis.

## Outcome & Insights

### 1. Industry Salary Trends

Finance has the highest average salary at $94,355.47, followed closely by Entertainment at $94,291.23 and Education at $93,798.52.

**Interpretation:** High-paying AI opportunities are not limited to the technology industry. Finance, media, education, energy, and healthcare all show strong compensation potential for AI-related roles.

### 2. Automation Risk and Salary

| Automation Risk | Job Count | Average Salary |
| --- | ---: | ---: |
| Medium | 173 | $87,786.44 |
| High | 169 | $93,907.53 |
| Low | 158 | $92,112.46 |

**Interpretation:** High automation-risk roles are not necessarily low-value roles. In this dataset, they have the highest average salary, suggesting that some risk-exposed roles still require specialized expertise and remain well compensated.

### 3. AI Adoption and Salary

| AI Adoption Level | Average Salary |
| --- | ---: |
| Low | $93,353.60 |
| Medium | $92,139.14 |
| High | $87,583.42 |

**Interpretation:** Higher AI adoption does not automatically lead to higher salaries. This could indicate that high-adoption companies may have standardized AI workflows, while lower-adoption companies may pay more for talent that helps them modernize.

### 4. Top Required Skills

| Skill | Frequency |
| --- | ---: |
| Python | 60 |
| Project Management | 60 |
| Cybersecurity | 58 |
| Machine Learning | 52 |
| UX/UI Design | 49 |
| Sales | 49 |
| Data Analysis | 49 |
| Marketing | 45 |
| JavaScript | 44 |
| Communication | 34 |

**Interpretation:** The market values both technical and business skills. Python, machine learning, cybersecurity, and data analysis remain important, but project management, sales, marketing, UX/UI, and communication also appear frequently.

### 5. Location Salary Trends

New York has the highest average salary at $93,780.43, followed by Singapore, Berlin, Tokyo, and Paris.

**Interpretation:** Strong salary markets are geographically diverse. Opportunities are not concentrated only in North American technology hubs.

### 6. Company Size Distribution

| Company Size | Job Count |
| --- | ---: |
| Small | 171 |
| Large | 166 |
| Medium | 163 |

**Interpretation:** AI job opportunities are distributed almost evenly across company sizes, meaning candidates should not limit their search to large enterprise employers.

## High-Level Insights

### 1. AI Careers Require Hybrid Skill Sets

Technical skills are highly visible, but the top skills list also includes project management, communication, sales, marketing, and UX/UI design. This suggests that AI-related careers reward professionals who can connect technical systems with business execution.

### 2. Automation Risk Should Be Interpreted Carefully

High automation risk does not necessarily mean low salary or poor opportunity. Some high-risk categories may pay more because they involve specialized tasks, transformation work, or roles that require humans to manage AI-enabled systems.

### 3. Industry Choice Matters

Finance, Entertainment, Education, and Energy outperform several other sectors in average salary. Candidates targeting AI roles should evaluate industry context instead of focusing only on job title.

### 4. AI Adoption Is Not a Standalone Salary Predictor

The dataset shows lower average salaries in high AI-adoption companies. This may reflect automation maturity, role standardization, or different hiring mixes. Compensation analysis should combine AI adoption with role, skill, industry, and location.

### 5. Location Still Influences Opportunity

Top salary locations include New York, Singapore, Berlin, Tokyo, Paris, and Sydney, showing that global markets offer competitive AI compensation.

## Business Impact

### Job Seekers

- Prioritize Python, project management, cybersecurity, machine learning, and data analysis.
- Evaluate automation risk alongside salary rather than avoiding high-risk categories automatically.
- Consider non-technology industries such as Finance, Entertainment, Education, and Energy.
- Expand job searches beyond traditional tech hubs to global salary leaders.

### Hiring Managers

- Benchmark salary offers against industry and location trends.
- Use skill frequency analysis to design realistic job descriptions.
- Recognize that hybrid technical/business skill combinations are valuable in AI roles.
- Review automation-risk exposure when planning workforce development.

### Educators and Career Coaches

- Build training paths that combine technical skills with communication, project delivery, and business analysis.
- Teach candidates how to interpret AI automation risk in a nuanced way.
- Use market evidence to guide reskilling and upskilling recommendations.

### Analysts and Business Stakeholders

- Use the SQL outputs and dashboard as a repeatable framework for labor-market analysis.
- Compare salary, risk, AI adoption, and skill demand together rather than in isolation.
- Extend the model to larger datasets or time-based labor market tracking.

## Project Structure

```text
AI_analytics_project/
├── README.md
├── ai_job_market_analysis.py
├── Senior_Analyst_AI_Market_Report.ipynb
├── ai_job_market_insights.csv
├── ai_jobs_cleaned.csv
├── ai_jobs.db
├── ai_jobs_summary.xlsx
├── AI Job Market Insight.twbx
├── requirements.txt
├── charts/
│   ├── 1_avg_salary_industry.png
│   ├── 2_automation_risk_donut.png
│   ├── 3_adoption_vs_salary.png
│   ├── 4_top_10_skills.png
│   ├── 5_salary_distribution_risk.png
│   ├── 6_company_size_risk_stacked.png
│   └── 7_avg_salary_location.png
└── sql_outputs/
    ├── 1_avg_salary_by_industry.csv
    ├── 2_job_count_and_salary_by_risk.csv
    ├── 3_top_10_required_skills.csv
    ├── 4_avg_salary_by_adoption.csv
    ├── 5_company_size_distribution.csv
    ├── 6_avg_salary_by_location_top10.csv
    ├── 7_automation_risk_by_industry.csv
    └── 8_top_10_job_titles.csv
```

## Quick Start

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Run the Full Pipeline

```bash
python ai_job_market_analysis.py
```

### 3. Review Generated Outputs

The pipeline generates:

- `ai_jobs_cleaned.csv`
- `ai_jobs.db`
- CSV query results in `sql_outputs/`
- PNG charts in `charts/`
- `ai_jobs_summary.xlsx`

### 4. Open the Tableau Workbook

Open `AI Job Market Insight.twbx` in Tableau Desktop or Tableau Reader to explore the local dashboard, or use the Tableau Public link in the dashboard section above.

### 5. Open the Notebook

```bash
jupyter notebook Senior_Analyst_AI_Market_Report.ipynb
```

## Requirements

See `requirements.txt` for package details.

Key dependencies:

- pandas
- plotly
- openpyxl
- tabulate
- kaleido, for static chart export if installed in the environment

## Future Work & Applications

- Expand the dataset with more job postings from multiple sources and dates.
- Add time-series analysis to track changes in salary, AI adoption, and skill demand.
- Use regression or tree-based models to estimate which variables most influence salary.
- Add SHAP values or feature importance analysis for model explainability.
- Build a Streamlit dashboard for browser-based exploration.
- Compare remote-friendly roles against salary, growth projection, and automation risk.
- Add natural language processing to analyze full job descriptions instead of single skill labels.

## Bottom Line

This project shows how AI job market data can be transformed into clear, decision-ready insights. By combining Python automation, SQL analysis, Excel reporting, and Tableau visualization, the project demonstrates a complete analytics workflow and highlights the importance of evaluating salary, risk, skills, industry, and geography together.
