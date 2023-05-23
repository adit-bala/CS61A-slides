---
marp: true
theme: uncover
class: invert
style: |
    section {
        font-size: 180%;
    }
    footer {
        font-size: .6em;
    }
paginate: true
footer: "Slides by Aditya Balasubramanian"
---

<!-- 
_paginate: false
_footer: Slides available at [`teaching.aditbala.com`](https://teaching.aditbala.com)
_class: invert
-->

# <!--fit--> Discussion 12

### SQL

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 8/2
_backgroundColor: #2222
-->

# Announcements :mega:

- Homework 9 due Thursday 4/20.
- Midterm 2 regrade requests due Friday 4/21.
- Optional Scheme Recursive Art Contest entries due Tuesday 4/25.
- Scheme project due Friday, 4/28.

    - Checkpoint 1 due Friday, 4/21.
    - Checkpoint 2 due Tuesday, 4/25.
    - Early submission point for submitting by Thursday, 4/27.
---

# SQL :book:

---

# SQL

* What is SQL?
    - A declarative programming language
    - Database management
    - Do not describe computations, but rather the desired result of computations
* Resources
    - https://sql.cs61a.org

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>    
# SELECT

- Create a table with two rows, columns as `first` and `last`

```sql
sqlite> SELECT "Ben" AS first, "Bitdiddle" AS last UNION
...> SELECT "Louis", "Reasoner";
```
| first      | last |
| :-----------: | :----------- |
| `Ben`      | 	`Bitdiddle`       |
| `Louis`   | `Reasoner`        |

```sql
SELECT [columns]
```

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style> 

# FROM

- SELECT specific values from an existing table with a FROM clause
```sql
sqlite> SELECT name, division FROM records;
```

| name      | division |
| :----------- | :----------- |
| `Alyssa P Hacker`      | 	`Computer`       |
| `...`   | `...`        |
| `Robert Cratchet` | `Accounting` |

```sql
SELECT [columns] FROM [tables]
```

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style> 

# WHERE

- filter out rows using a WHERE clause

```sql
sqlite> SELECT * FROM records WHERE title = "Programmer";
```

| name      | division | title | salary | supervisor
| :----------- | :----------- | :------ | :------ | :------ |
| Alyssa P Hacker | Computer | Programmer | 40000 | Ben Bitdiddle |
| Cy D Fect | Computer | Programmer | 35000 | Ben Bitdiddle |


```sql
SELECT [columns] FROM [tables] WHERE [condition]
```

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style> 

# ORDER BY

- Order rows with the ORDER BY clause

```sql
sqlite> SELECT name, salary FROM records
...> WHERE division = "Accounting" ORDER BY salary desc;
```

| name      | salary |
| :----------- | :----------- |
| `Eben Scrooge`      | 	`75000`       |
| `Robert Cratchet` | `18000` |

```sql
SELECT [columns] FROM [tables] WHERE [condition] 
ORDER BY [criteria]
```

---

# `Q4`, `Q5`, `Q6`

---

# JOIN

* What to do when you want to combine data from mutliple tables
    - JOIN them!
* What happens when you use the JOIN clause?
    - Have a new row for each combination of the input table
    -  If two tables are joined and the left table has `m` rows and the right table has `n` rows, then the joined table will have `m*n` rows

---

# JOIN (Example)

* Let's say we have a `meetings` table that displays what `Day` each `Division` has a meeting
* Our goal is to determine what `Day` each employee has a meeting
* First step
    - Combine table `records` and `meetings`
* Second step
    - Only include the rows where the 
    `records.division` = `meetings.division`

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style> 
# JOIN (Example) (Combining)

```sql
SELECT name, day FROM records, meetings;
```

| name      | day |
| :----------- | :----------- |
| `Alyssa P Hacker`      | 	`Monday`       |
| `Alyssa P Hacker` | `Monday` |
| `Alyssa P Hacker`      | 	`Wednesday`       |
| `Alyssa P Hacker` | `Wednesday` |
| `...` | `...` | 
| `Robert Cratchet` | `Wednesday` |

---
<style scoped>
  pre > code {
    font-size: 160%;
  }
</style> 
# JOIN (Example) (Filtering)

Ambigious Joins

```sql
SELECT a.name, b.day FROM records AS a, meetings AS b 
WHERE a.division = b.division;
```

| name      | day |
| :----------- | :----------- |
| `Alyssa P Hacker`      | 	`Wednesday`       |
| `Ben Bitdiddle` | `Wednesday` |
| `...` | `...` | 
| `Robert Cratchet` | `Monday` |

`STEP BY STEP`


---

# `Q6`, `Q7`, `Q8`

---
<style scoped>
  pre > code {
    font-size: 160%;
  }
</style> 

# Aggregation

* What if we want to obtain data from our table (i.e `max`, `min`)
    - `MAX`, `MIN`, `COUNT`, and `SUM`
```sql
SELECT name, MAX(salary) FROM records;
```
| name      | MAX(salary) |
| :----------- | :----------- |
| `Oliver Warbucks`      | 	`150000`       |
```sql
sqlite> SELECT COUNT(*) from RECORDS;
9
```
---
<style scoped>
  pre > code {
    font-size: 160%;
  }
</style> 

# GROUP BY

* group rows in a column to be aggregated with the GROUP BY clause

```sql
sqlite> SELECT division, MIN(salary) FROM records 
GROUP BY division;
```

| division      | MIN(salary) |
| :----------- | :----------- |
| `Accounting`      | 	`18000`       |
| `Administration`      | 	`150000`       |
| `Computer`      | 	`25000`       |

`STEP BY STEP`

---
<style scoped>
  pre > code {
    font-size: 160%;
  }
</style>
# HAVING

- Filter GROUPS with the HAVING clause

```sql
sqlite> SELECT title FROM records GROUP BY title 
HAVING COUNT(*) > 1;
```

| title |
| :-----|
| `Programmer` |

`STEP BY STEP`

---

# `Q9`, `Q10`, `Q11`

---
# Thank you!!! 

### Anon Feedback -> https://tinyurl.com/adit-anon
