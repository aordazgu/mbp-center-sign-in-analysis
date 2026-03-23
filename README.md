# MBP Center Sign-In Analysis (AY 24–25 & AY 25–26)

A data analysis of student sign-in patterns at the MBP (Multicultural Business Program) Center at Cal Poly, spanning academic years 2024–25 and 2025–26. The report is built in R and Quarto and is designed to directly support staffing, supply budgeting, and funding decisions.

## What This Project Does

The MBP Center collects sign-in data each time a student visits and selects the resources they plan to use. This project takes that raw sign-in data and produces a decision-ready report that answers:

- **How many students are using the center?** Total visits, unique students, and visits per open day.
- **What do students need most?** Resource demand measured by both total selections and percent of visits — since students can select multiple resources per visit.
- **When is demand highest?** Day-of-week, hour-of-day, and weekly trends, including a day-by-hour heatmap for staffing decisions.
- **Are students coming back?** Repeat visitor rates, return timing (within 7 days, 30 days), and median days between visits.
- **How does this year compare to last year?** Year-over-year comparison using a fair method that limits both years to the same stage of the academic calendar.
- **What should the program do about it?** Direct recommendations for staffing, supply budgeting, and funding proposals.

## Report Structure

| Section | What It Covers |
|:--------|:---------------|
| Executive Summary | Standalone overview with key findings, top resources, and recommended actions |
| Data Quality | Missing values, duplicate detection, identifier consistency, resource label cleanup |
| Year-over-Year Comparison | Same-stage comparison of visits, unique students, and resource demand across years |
| AY 25–26 Full-Year Analysis | Usage summary, engagement distribution, repeat visitor deep dive, peak day/hour analysis |
| Resource Analysis | Individual resources with % of visits; categories (Basic Needs, Academic Support, Community & Belonging) |
| Normalized Metrics | Visits per open day, unique students per month, resource selections per 100 visits |
| Recommendations | Staffing, supply budgeting, retention, and data collection actions tied to findings |
| Funding-Ready Summary | Talking points designed to be copied into budget requests and memos |
| Limitations | What the data can and cannot tell us |

## Tech Stack

- **R** — Data wrangling, analysis, and visualization
- **Quarto** — Literate programming and report generation
- **tidyverse** — Core data manipulation and ggplot2 visualizations
- **lubridate** — Date and time parsing
- **janitor** — Data cleaning
- **scales** — Number formatting
- **knitr / kableExtra** — Table rendering and styling

## Project Structure

```
mbp-center-sign-in-analysis/
├── MBP Sign-in Data Analysis AY 24-26.qmd   # Main Quarto report (source)
├── MBP Sign-in Data Analysis AY 24-26.html   # Rendered HTML report
├── MBP Center Sign-In, AY 24-25.csv          # AY 24–25 sign-in data
├── MBP Center Sign-In, AY 25-26.csv          # AY 25–26 sign-in data
├── MBP Center Sign-In, AY 24-25.xlsx         # AY 24–25 data (Excel)
├── MBP Center Sign-In, AY 25-26.xlsx         # AY 25–26 data (Excel)
└── README.md
```

## How to Render the Report

1. Install [R](https://cran.r-project.org/) and [Quarto](https://quarto.org/docs/get-started/).
2. Install required R packages:
   ```r
   install.packages(c("tidyverse", "lubridate", "janitor", "scales", "knitr", "kableExtra"))
   ```
3. Render from the terminal:
   ```bash
   quarto render "MBP Sign-in Data Analysis AY 24-26.qmd"
   ```
   This produces a self-contained HTML file.

## Data Notes

- Each row in the CSV files represents one **visit** (sign-in event).
- Students self-report the resources they plan to use; one visit can include multiple resource selections.
- Student usernames are entered manually, so minor inconsistencies (typos, capitalization) may exist. The analysis normalizes these where possible.
- The rendered report includes a full data quality section and limitations discussion.

## Author

**Arturo Ordaz-Gutierrez** — MBP Logistics & MBPC Committee, Cal Poly
