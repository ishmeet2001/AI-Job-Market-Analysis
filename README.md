# AI Job Market Insights - Data Analysis Project

## 📊 Project Overview

A comprehensive **end-to-end data analysis pipeline** exploring the AI job market landscape. This project demonstrates proficiency in **data cleaning, SQL analytics, Python visualization, and business intelligence** to answer critical questions for job seekers navigating the AI industry.

### Key Questions Answered:
1. **Which industries pay the most and is it worth the automation risk?**
2. **Does AI adoption actually translate to higher salaries?**
3. **What skills should someone prioritize to future-proof their career?**
4. **Do larger companies actually pay more or is that a myth?**
5. **Which locations offer the best salary opportunities?**

---

## 📈 Dataset

- **Source**: `ai_job_market_insights.csv`
- **Records**: 1,000+ AI job postings
- **Columns**: Job Title, Industry, Location, Salary USD, Company Size, AI Adoption Level, Automation Risk, Required Skills
- **Coverage**: Global locations (US, UK, EU, Asia-Pacific)

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Data Processing** | Python 3.11, Pandas |
| **Database** | SQLite3 |
| **Visualization** | Plotly (Python) |
| **BI Dashboard** | Tableau Desktop/Public |
| **Excel Reporting** | Openpyxl |

---

## 📦 Project Structure

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

## 🚀 Quick Start

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

**Output generated:**
- ✅ `ai_jobs_cleaned.csv` - Cleaned dataset
- ✅ `ai_jobs.db` - SQLite database with 8 analytical queries
- ✅ `charts/` - 7 Plotly PNG visualizations
- ✅ `sql_outputs/` - 8 CSV query results
- ✅ `ai_jobs_summary.xlsx` - Formatted Excel workbook with pivot tables

### View the Jupyter Notebook

```bash
jupyter notebook Senior_Analyst_AI_Market_Report.ipynb
```

Explore 5 key analytical questions with visualizations and actionable insights for job seekers.

---

## 📊 Tableau Dashboard

### View Interactive Dashboard

**Option 1: Open Locally (Requires Tableau Desktop)**
```
File: AI Job Market Insight.twbx
Open with: Tableau Desktop or Tableau Reader (free)
```

**Option 2: Publish to Tableau Public (Free Online Sharing)**

1. **Open the dashboard in Tableau Desktop:**
   - File → Open → `AI Job Market Insight.twbx`

2. **Publish to Tableau Public:**
   - File → Save As → Select "Tableau Public"
   - Sign in with your Tableau Public account (create free at https://public.tableau.com)
   - Choose sheet tabs to publish
   - Click "Publish"

3. **Share the link:**
   - Copy the public URL generated after publishing
   - Share with stakeholders or include in portfolio

**Option 3: Embed in Portfolio Website**
```html
<!-- After publishing to Tableau Public, embed using iframe: -->
<iframe src="https://public.tableau.com/views/[YOUR_WORKBOOK]/[YOUR_SHEET]" 
        width="800" height="600"></iframe>
```

**Dashboard Features:**
- Interactive filters by Industry, Location, Company Size
- Salary trends by automation risk
- AI adoption correlation analysis
- Skill frequency heatmaps
- Geographic distribution mapping

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

### 🎯 Skills to Prioritize
1. **Python** (60% of postings)
2. **Machine Learning** (45%)
3. **Data Analysis** (55%)
4. **SQL** (50%)
5. **Strategic Project Management** (differentiation factor)

---

## 📋 Pipeline Steps

### Step 1: Data Cleaning & Profiling
- Load and profile dataset
- Handle missing values
- Standardize categorical variables
- Drop duplicates

### Step 2: SQL Analysis
8 analytical queries executed on SQLite:
- Average salary by industry
- Job count & salary by automation risk
- Top 10 required skills
- Salary by AI adoption level
- Company size distribution
- Top locations by salary
- Automation risk by industry
- Top job titles

### Step 3: Python Visualizations
7 Plotly charts with professional Tableau-inspired styling:
- Horizontal bar charts
- Donut/pie charts
- Grouped bar charts
- Box plots
- Stacked bar charts

### Step 4: Excel Report
Multi-sheet workbook with:
- Cleaned dataset
- Industry pivot table summary
- Top 10 skills frequency table
- Professional formatting & styling

---

## 📖 How to Use This Project

### For Portfolio Presentation:
1. Show cleaned/processed data quality
2. Highlight SQL query complexity & business logic
3. Display interactive Tableau dashboard
4. Reference Jupyter notebook insights
5. Mention Excel formatting for stakeholder reporting

### For Hiring Managers:
- **Data Cleaning**: Demonstrated with missing value handling & standardization
- **SQL**: 8 complex queries across multiple dimensions
- **Python**: Pandas, Plotly, Openpyxl expertise
- **BI Tools**: Tableau dashboard creation & publishing
- **Analytics**: Business question formulation & actionable insights

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| `ModuleNotFoundError: No module named 'plotly'` | Run `pip install -r requirements.txt` |
| Charts not saving | Ensure Kaleido is installed: `pip install kaleido` |
| Tableau file won't open | Install Tableau Reader (free) or Tableau Desktop |
| Database locked error | Close all existing connections to `ai_jobs.db` |

---

## 📝 Requirements

See `requirements.txt` for complete package list with versions.

**Key dependencies:**
- pandas ≥ 1.3.0
- plotly ≥ 5.0.0
- openpyxl ≥ 3.0.0
- tabulate ≥ 0.8.9

---

## 👤 Author
**Portfolio Project**: AI Job Market Insights Analysis  
**Role**: Analytics & Insights Analyst  
**Date**: April 2025

---

## 📄 License
This project and all outputs are for portfolio demonstration purposes.

---

## 🤝 Feedback & Questions
For questions about methodology, findings, or technical implementation, refer to:
- `ai_job_market_analysis.py` - Code comments & documentation
- `Senior_Analyst_AI_Market_Report.ipynb` - Detailed insights & narrative
- SQL query results in `sql_outputs/` for data validation
