# 🎓 Exploring International Students' Mental Health Using SQL

## 📘 Project Overview

This project analyzes how the **length of stay** impacts the **mental health scores** of international students in a Japanese university. Using PostgreSQL, I explored relationships between students' duration of stay and their levels of:

- Depression (PHQ-9 test)
- Social connectedness (SCS test)
- Acculturative stress (ASISS test)

> ✅ **Goal:** Understand whether mental health improves or worsens over time for international students and support insights with data.

---

## 📊 Dataset Description

The dataset contains survey responses from international and domestic students. Key columns used:

| Column Name | Description |
|-------------|-------------|
| `inter_dom` | Type of student (International or Domestic) |
| `stay` | Length of stay in years |
| `todep` | Depression score (PHQ-9 test) |
| `tosc` | Social connectedness score (SCS test) |
| `toas` | Acculturative stress score (ASISS test) |

---

## 🧠 Key Question

> **Does the length of stay affect mental health outcomes for international students?**

---
## 🔍 SQL Query Used
```sql
SELECT stay,
       COUNT(*) AS count_int, 
       ROUND(AVG(todep), 2) AS average_phq, 
       ROUND(AVG(tosc), 2) AS average_scs,
       ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```
---
## Results
| stay | count_int | average_phq | average_scs | average_as |
|------|-----------|-------------|-------------|------------|
| 10   | 1         | 13.00       | 32.00       | 50.00      |
| 8    | 1         | 10.00       | 44.00       | 65.00      |
| 7    | 1         | 4.00        | 48.00       | 45.00      |
| 6    | 3         | 6.00        | 38.00       | 58.67      |
| 5    | 1         | 0.00        | 34.00       | 91.00      |
| 4    | 14        | 8.57        | 33.93       | 87.71      |
| 3    | 46        | 9.09        | 37.13       | 78.00      |
| 2    | 39        | 8.28        | 37.08       | 77.67      |
| 1    | 95        | 7.48        | 38.11       | 72.80      |

🧠 Insights
Students staying longer than 6 years showed lower average depression scores but varying levels of stress and social connectedness.

The largest group had just 1–3 years of stay, with higher acculturative stress and moderate social connectedness.

A longer stay does not always mean improved mental health, but social connectedness appears to improve with time.

🚀 Skills Practiced
Filtering data using WHERE

Aggregating with AVG() and COUNT()

Using GROUP BY and sorting results

Applying ROUND() for cleaner output

Thinking critically about real-world survey data

📌 Tools Used
SQL (PostgreSQL)

DataCamp SQL Workspace

📚 Context
Based on a 2018 study conducted by a Japanese international university, which concluded that:

"International students are at greater risk of mental health challenges. Social connectedness and acculturative stress are strong predictors of depression."

This project was an effort to validate those findings using structured query language.

✅ Completed As Part Of:
📍 Analyzing Students' Mental Health

📆 Date: June 2025

Platform: DataCamp

