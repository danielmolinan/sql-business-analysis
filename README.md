# SQL Business Analysis
Repository of business analyses carried out with SQL, combining technical queries with decision-oriented interpretation. The cases are based on real datasets used during the **Master's in Data Science, Big Data & Business Analytics** at Universidad Complutense de Madrid. The data can be downloaded from the following link:

[💾Datasets](https://drive.google.com/drive/folders/16X_SxwOKAlhnYZBA5g1B-MgfmGd2zSeE?usp=sharing)

---

## Analysis cases

### [Smart Desk — Global Sales Analysis (2019–2021)](./smart-desk-case/)

**Context:** Smart Desk is a company with a presence across four global regions (NAM, EMEA, APAC, and LATAM). The analysis covers the 2019–2021 period, coinciding with the impact of COVID-19 on the global economy, and seeks to answer a specific business question:

> *Which region had the best and worst performance in sales and profit between 2019 and 2021, and what factors explain it?*

**Database:** Snowflake · Schema `SMART_DESK` · Tables: `SALES`, `ACCOUNTS`, `FORECASTS`

**Analyses performed:**

| # | Analysis | SQL techniques used |
|---|----------|------------------------|
| 1 | Sales and profit by product category (Adabs Entertainment account, 2020) | `WHERE`, `TO_VARCHAR`, numeric formatting |
| 2 | Performance comparison by country in the APAC and EMEA regions | `INNER JOIN`, `GROUP BY`, `AVG`, `ORDER BY` |
| 3 | Profit by industry among clients in the engagement stage | multiple `INNER JOIN`, subquery with `IN`, `CASE WHEN`, `SUM` |
| 4 | Forecast vs. actual profit evolution by category | `FULL OUTER JOIN`, `COALESCE`, `MIN`/`MAX` |
| 5 | Open-ended exploratory analysis: regional performance during COVID-19 | `INFORMATION_SCHEMA`, `CASE WHEN`, `COUNT DISTINCT`, multidimensional analysis |

**Key findings:**
- NAM (United States) led historical sales with ~$98M, closely followed by EMEA with ~$97M, while LATAM lagged far behind with ~$7M.
- Despite COVID-19, Smart Desk's global sales grew year over year: +28% between 2019 and 2020, and +31% between 2020 and 2021.
- APAC showed anomalous behavior: it tripled its sales between 2019 and 2020, but dropped 36% in 2021 — the only case of decline that year.
- NAM's sales fell in 2020 (the only year affected by the pandemic) but doubled in 2021, reaching ~$44M.
- Singapore generated higher average revenue than Germany despite having a population 13 times smaller.

**Recommendations derived from the analysis:**
- Diversify markets in LATAM (Brazil, Colombia, Chile) to reduce dependence on Argentina and Mexico.
- Investigate APAC's 2021 decline, especially the absence of Singapore following its exceptional 2020 performance.
- Evaluate adding Canada to the NAM region to reduce dependence on a single market.
- Study the factors that allowed France, Spain, Australia, and Singapore to grow in 2020, in order to replicate them in weaker markets.

---

## SQL techniques demonstrated
- Joins: `INNER JOIN`, `FULL OUTER JOIN`
- Aggregations: `SUM`, `AVG`, `COUNT DISTINCT`, `MIN`, `MAX`, `ROUND`
- Conditional logic: `CASE WHEN`, `COALESCE`
- Correlated subqueries with `IN`
- Schema exploration with `INFORMATION_SCHEMA.COLUMNS`
- Output formatting with `TO_VARCHAR` and numeric masks
- Multidimensional sorting and filtering

**Platform:** Snowflake (standard SQL compatible)

---

## Repository structure
```
sql-business-analysis/
│
└── smart-desk-case/
    ├── smart_desk_analysis.sql   # Full queries with comments
    └── smart_desk_report.pdf     # Analysis and interpretation of results
```

---

## Author
**Daniel Molina Novoa** · Data Analyst
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/daniel-molina-novoa/)
[![GitHub](https://img.shields.io/badge/GitHub-danielmolinan-181717?style=flat&logo=github&logoColor=white)](https://github.com/danielmolinan)
