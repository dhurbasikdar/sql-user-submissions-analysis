# SQL User Submissions Analysis

SQL project in PostgreSQL that analyses user submission data from a coding practice platform. It answers questions about user performance, activity, and rankings.

## Tech Stack
- PostgreSQL 18
- pgAdmin 4

## Dataset
Table: `user_submissions` (47 users)
- `username`
- `id`
- `points`
- `submitted_at`
- `result` (correct / incorrect)

## Questions Solved
1. List all distinct users with total submissions and points earned
2. Daily average points for each user
3. Top 3 users with the most correct submissions each day
4. Top 5 users with the most incorrect submissions
5. Top 10 performers for each week

## SQL Concepts Used
- `GROUP BY` and aggregates (`COUNT`, `SUM`, `AVG`)
- `FILTER` clause for conditional counts
- Window functions: `RANK() OVER (PARTITION BY ...)`
- `DATE()` and `DATE_TRUNC()` for day/week grouping
- Subqueries

## Sample Query
```sql
SELECT username,
       COUNT(id) AS total_submissions,
       SUM(points) AS points_earned
FROM user_submissions
GROUP BY username
ORDER BY total_submissions DESC;
```

## How to Run
1. Create a database in PostgreSQL
2. Import the `user_submissions` data
3. Open `project_files.sql` in pgAdmin
4. Run the queries one by one

## Author
Dhurba
