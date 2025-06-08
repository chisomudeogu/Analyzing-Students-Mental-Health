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
