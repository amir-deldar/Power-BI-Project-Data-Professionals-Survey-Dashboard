# 📊 Data Professional Survey Breakdown Dashboard

An interactive **Power BI** dashboard that explores the results of a survey of **630 data professionals** — what they earn, which tools they use, how happy they are at work, and how hard it was to break into the field.

## 🎯 Project Overview

People entering the data field often ask the same questions: *Which role pays the most? Which language should I learn? Is it hard to get in? Will I be happy?*

This project answers them with a one-page Power BI dashboard built on real survey responses. It covers the full analyst workflow — importing raw Excel data, cleaning and transforming it in **Power Query**, and presenting insights through clear, interactive visuals.

## ❓ Business Questions

1. How does average salary differ across data job titles?
2. Which programming languages do data professionals prefer?
3. Where do survey respondents live?
4. How satisfied are professionals with their salary and work/life balance?
5. How difficult was it to break into the data field?

## 📁 Dataset

| Item | Detail |
|---|---|
| Source | Data Professional Survey (Excel) |
| Responses | 630 |
| Collected | 10–26 June 2022 |
| Format | `.xlsx` (1 sheet, 28 raw columns) |

**Survey fields:** job title, career switch (yes/no), salary range, industry, favorite programming language, happiness ratings (0–10) for six job aspects — salary, work/life balance, coworkers, management, upward mobility and learning new things — difficulty of breaking into data, most important factor in a new job, gender, age, country, education and ethnicity.

## 🧹 Data Preparation (Power Query)

All cleaning was done in Power Query so the source file stays untouched:

- **Removed unused columns** — Browser, OS, City, Country, Referrer (empty for every respondent).
- **Standardized free-text answers** — split on delimiters to collapse write-in values such as `Other (Please Specify): …` into a single **"Other"** category for:
  - Job title (Q1)
  - Industry (Q4)
  - Programming language (Q5)
  - Country (Q11)
- **Converted salary ranges to a numeric value** — salary was collected as bands (e.g. `41k-65k`). I extracted the lower and upper bound, and created an **`Average Salary`** column using the band midpoint (`(low + high) / 2`, in $K). The open-ended `225k+` band is treated as 225.
- **Set correct data types** — dates, times, integers (happiness scores, age) and text.

## 📈 Dashboard Components

| Visual | Type | What it shows |
|---|---|---|
| Survey Takers' Age | Card | Respondent age summary |
| Average Salary by Job Title | Bar chart | Mean salary midpoint per role |
| Favorite Programming Language | Column chart (stacked by job title) | Language popularity, split by role |
| Country of Survey Takers | Treemap | Geographic mix of respondents |
| Happiness with Salary | Gauge | Satisfaction with pay |
| Happiness with Work/Life Balance | Gauge | Satisfaction with balance |
| Difficulty to Break into Data | Donut chart | Perceived entry difficulty |

All visuals are cross-filterable, so clicking a job title, language or country updates the whole page.

## 🔍 Key Findings

> Figures are calculated from the 630 responses. Salaries use band midpoints, so treat them as estimates.

### 💰 Salary
- **Data Scientists earn the most** — about **$94K** average, well ahead of Data Engineers (**$65K**) and Data Analysts (**$55K**).
- Overall, respondents average **~$54K** (median ≈ $53K). **44%** of respondents earn **under $40K**, and only ~5% earn $125K or more.
- Students / job-seekers average about $27K, as expected.

### 👩‍💻 Roles & Tools
- **Data Analysts are the largest group** — 381 of 630 respondents (**60%**), followed by Data Engineers (38) and Data Scientists (25).
- **Python is the clear favorite** language — **67%** of respondents (420), roughly 4× more than R (101, 16%). Python is the top pick in **every** job title.

### 🌍 Who Responded
- **United States** leads with **261 respondents (41%)**, then India (73), the UK (40) and Canada (32).
- The respondent base is young: median age **28**, and ~**74%** are male.
- **53%** hold a Bachelor's and **31%** a Master's degree. **59%** switched careers into data from another field.

### 😊 Happiness at Work (average rating out of 10)
| Aspect | Avg. score |
|---|---|
| Coworkers | 5.86 |
| Work/Life Balance | 5.74 |
| Learning New Things | 5.61 |
| Management | 5.33 |
| Upward Mobility | 4.76 |
| **Salary** | **4.27** |

- **Salary is the lowest-rated aspect (4.3)**, while **work/life balance (5.7)** and coworkers score noticeably higher.

### 🚪 Breaking Into Data
- **43%** found it *neither easy nor difficult*.
- About **32%** found it difficult or very difficult, versus **26%** who found it easy or very easy — so entry is a moderate, not extreme, hurdle.

### 🎯 What Matters in a New Job
- **Better salary** is the top priority for **47%** of respondents, followed by remote work (20%) and work/life balance (19%). This lines up with the low salary-satisfaction score.

## 💡 Recommendations

- **For aspiring analysts:** Learn **Python** first — it is the most popular language in every role, and moving toward data science / engineering is where the biggest pay jumps are in this sample.
- **For employers:** Pay is the main weakness and main motivator. Competitive compensation — plus remote flexibility — is the biggest retention lever suggested by this data.
- **For career changers:** Over half of respondents switched into data and most rated entry as moderate in difficulty, so a non-traditional background is common and workable.

**Planned improvements**
- Add slicers (job title, country, industry, gender).
- Show average happiness across all six aspects, not just two.
- Break down salary by country, education and career-switcher status.
- Use **average** age and happiness scores in the card and gauges, and add DAX measures for percentages.

## 🛠 Tools & Skills Demonstrated

- **Power BI Desktop** — report design, interactive visuals
- **Power Query (M)** — data cleaning, column splitting, type conversion, custom columns
- **Data modeling & calculated columns**
- **Data visualization** — bar, column, treemap, gauge and donut charts
- **Data storytelling** — turning survey data into business insights
- **Excel** — source data

## 🗂 Repository Structure

```
├── 📁 data/
│   └── Data_Professionals.xlsx
├── 📁 dashboard/
│   └── Data_Professional_Survey_Breakdown_Dashboard.pbix
├── 📁 images/
│   └── dashboard.png
└── README.md
```


**Author: Amir Deldar**

## 📬 Contact:

[LinkedIn](https://www.linkedin.com/in/amirdeldar) · [GitHub](https://github.com/amir-deldar) · Email: <callmedeldar@gmail.com>
