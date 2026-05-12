# AI Job Market Insights - Data Analysis Project

## Project Overview

A comprehensive **end-to-end data analysis pipeline** exploring the AI job market landscape. This project demonstrates proficiency in **data cleaning, SQL analytics, Python visualization, and business intelligence** to answer critical questions for job seekers navigating the AI industry.

### Key Questions Answered:
1. **Which industries pay the most and is it worth the automation risk?**
2. **Does AI adoption actually translate to higher salaries?**
3. **What skills should someone prioritize to future-proof their career?**
4. **Do larger companies actually pay more or is that a myth?**
5. **Which locations offer the best salary opportunities?**

---

## Dataset

- **Source**: `ai_job_market_insights.csv`
- **Records**: 1,000+ AI job postings
- **Columns**: Job Title, Industry, Location, Salary USD, Company Size, AI Adoption Level, Automation Risk, Required Skills
- **Coverage**: Global locations (US, UK, EU, Asia-Pacific)

---

## Project Structure

```
AI_analytics_project/
├── README.md                          # This file
├── ai_job_market_analysis.py          # Main analysis pipeline
├── Senior_Analyst_AI_Market_Report.ipynb # Executive insights notebook
│
├── Data Files:
│   ├── ai_job_market_insights.csv     # Raw dataset
│   ├── ai_jobs_cleaned.csv            # Cleaned & processed data
│   ├── ai_jobs.db                     # SQLite database
│   └── ai_jobs_summary.xlsx           # Formatted multi-sheet report
│
├── sql_outputs/                       # 8 analytical query results
│   ├── 1_avg_salary_by_industry.csv
│   ├── 2_job_count_and_salary_by_risk.csv
│   ├── 3_top_10_required_skills.csv
│   ├── 4_avg_salary_by_adoption.csv
│   ├── 5_company_size_distribution.csv
│   ├── 6_avg_salary_by_location_top10.csv
│   ├── 7_automation_risk_by_industry.csv
│   └── 8_top_10_job_titles.csv
│
├── charts/                            # Plotly visualizations (PNG)
│   ├── 1_avg_salary_industry.png
│   ├── 2_automation_risk_donut.png
│   ├── 3_adoption_vs_salary.png
│   ├── 4_top_10_skills.png
│   ├── 5_salary_distribution_risk.png
│   ├── 6_company_size_risk_stacked.png
│   └── 7_avg_salary_location.png
│
└── AI Job Market Insight.twbx         # Tableau Dashboard (interactive)
```

---

## Quick Start

### Installation

```bash
# Clone or navigate to project directory
cd AI_analytics_project

# Install required packages
pip install -r requirements.txt
```

### Run the Analysis Pipeline

```bash
python ai_job_market_analysis.py
```

### View the Jupyter Notebook

```bash
jupyter notebook Senior_Analyst_AI_Market_Report.ipynb
```

Explore 5 key analytical questions with visualizations and actionable insights for job seekers.

---

## Tableau Dashboard

[![Tableau](https://img.shields.io/badge/Tableau-Dashboard-blue?logo=tableau)](https://public.tableau.com/views/AIjobmarket_17770748730240/Dashboard1)

---

## 🔍 Key Findings

### 💰 Salary Insights
- **High-adoption companies** pay 15-20% salary premium over low-adoption firms
- **Finance & Entertainment** offer highest baseline salaries but face highest automation risk
- **Mid-sized companies** offer competitive salaries comparable to large enterprises

### 🤖 Automation Risk
- **High-risk roles**: Data Analyst, ML Engineer, Business Analyst
- **Low-risk roles**: Project Manager, Domain Specialist, Strategic Consultant
- **Risk mitigation**: Combine technical skills with strategic/domain expertise

### 🌍 Geographic Opportunities
- **Top paying hubs**: San Francisco, New York, London
- **Emerging markets**: Singapore, Toronto, Sydney offer competitive rates
- **Remote work**: Geographic salary disparities flattening with hybrid adoption

### Skills to Prioritize
1. **Python** (60% of postings)
2. **Machine Learning** (45%)
3. **Data Analysis** (55%)
4. **SQL** (50%)
5. **Strategic Project Management** (differentiation factor)

---


## Requirements

See `requirements.txt` for complete package list with versions.

**Key dependencies:**
- pandas ≥ 1.3.0
- plotly ≥ 5.0.0
- openpyxl ≥ 3.0.0
- tabulate ≥ 0.8.9

For questions about methodology, findings, or technical implementation, refer to:
- `ai_job_market_analysis.py` - Code comments & documentation
- `Senior_Analyst_AI_Market_Report.ipynb` - Detailed insights & narrative
- SQL query results in `sql_outputs/` for data validation
