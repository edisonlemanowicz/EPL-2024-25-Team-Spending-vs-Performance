EPL 2024-25: Team Spending vs Performance
Description

Analyzed 2024-25 English Premier League team wage spending vs performance. Used SQL to join wages and standings, calculated points per million and overperformance scores, and visualized results in Tableau. Highlights teams that outperform or underperform relative to spending.

Objective

Explore how financial investment in team wages correlates with league success and efficiency.

Data Sources

EPL Team Wage Data 2024-25

EPL 2024-25 Standings

Methods

Loaded datasets into SQL and joined on team and season

Calculated:

Points per million spent (points / wage_spend_millions)

Spending rank and performance rank

Overperformance score (performance rank − spending rank)

Exported cleaned dataset (epl_sql_scatter.csv) for visualization

SQL Example
SELECT
    w.team,
    w.wage_spend_millions,
    s.points,
    ROUND(s.points / w.wage_spend_millions, 2) AS points_per_million,
    RANK() OVER (ORDER BY w.wage_spend_millions DESC) AS spend_rank,
    RANK() OVER (ORDER BY s.points DESC) AS performance_rank,
    (RANK() OVER (ORDER BY s.points DESC) - RANK() OVER (ORDER BY w.wage_spend_millions DESC)) AS overperformance_score
FROM wages w
JOIN standings s
ON w.team = s.team AND w.season = s.season

Visualization

Scatter Plot: Wage Spending (X-axis) vs Points (Y-axis)

Bubble Size: Overperformance score

Color: Points per million spent (efficiency)

Trend Line: Linear regression showing general correlation

Insights: Higher spending doesn’t always guarantee top performance; strategic investment can yield better efficiency

![Scatter Plot](Spending vs Performance.pdf)

Files

wages.csv – Team wage data

standings.csv – League standings

epl_sql_scatter.csv – Merged dataset with calculated metrics

Spending vs Performance.pdf – Scatter plot visualization

Insights

Liverpool and Arsenal outperformed their wage investment

Some high-spending teams, like Manchester United, underperformed

Efficiency and strategy matter more than raw spending for league success
