Netflix Shows and Movies Analysis 📊
<p align="center"> <img src="images/netflix_logo.png" alt="Netflix Logo" width="200"/> </p>
Project Overview

This project analyzes Netflix’s movies and shows dataset to extract meaningful insights using SQL and Tableau.
The dataset contains approximately 82,000 rows, making manual analysis inefficient.

Tools Used

Excel – Initial data exploration

MySQL – Data cleaning and analysis

Tableau – Interactive dashboard

Dataset

Netflix Movies & Shows dataset

Fields: title, type, release year, IMDB score, age certification, genres

Business Problem

Netflix wants to understand content performance and audience preferences but is working with a very large dataset. The challenge is to efficiently extract insights and trends that support decision-making.

Solution Approach

Used SQL for querying, filtering, and aggregations

Analyzed ratings, decades, genres, and age certifications

Built a Tableau dashboard for interactive visualization

SQL Analysis (Code Samples)
Top 10 Movies by IMDB Score
SELECT title, type, imdb_score
FROM shows_movies.titles
WHERE imdb_score >= 8.0
AND type = 'MOVIE'
ORDER BY imdb_score DESC
LIMIT 10;


📌 Query Output Screenshot

![Top 10 Movies SQL](images/top_10_movies_sql.png)

Movies & Shows by Decade
SELECT CONCAT(FLOOR(release_year / 10) * 10, 's') AS decade,
       COUNT(*) AS movies_shows_count
FROM shows_movies.titles
WHERE release_year >= 1940
GROUP BY decade
ORDER BY decade;


📌 Result Screenshot

![Decade Distribution](images/decade_distribution.png)

Tableau Dashboard

The Tableau dashboard provides:

Genre-wise distribution

Rating trends

Content growth by decade

Interactive filters

📊 Dashboard Screenshot

![Netflix Tableau Dashboard](images/netflix_tableau_dashboard.png)

Key Insights

Comedy is the most dominant genre

Content increased significantly after the 2000s

TV-14 content has the highest average IMDB score

Multi-genre titles perform well

Conclusion

This analysis helps Netflix understand audience preferences, content trends, and performance gaps. The insights can support better recommendation systems, content acquisition, and strategic planning.

Folder Structure (Recommended)
Netflix-Analysis/
│
├── images/
│   ├── netflix_logo.png
│   ├── top_10_movies_sql.png
│   ├── decade_distribution.png
│   └── netflix_tableau_dashboard.png
│
├── sql/
│   └── analysis_queries.sql
│
└── README.md
