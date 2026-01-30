# EPL 2024-25: Team Spending vs Performance

## Description
Analyzed 2024-25 English Premier League team wage spending vs performance. Used SQL to join wages and standings, calculated points per million and overperformance scores, and visualized results in Tableau. Highlights teams that outperform or underperform relative to spending.

## Objective
To explore how financial investment in team wages correlates with league success and efficiency.

## Data Sources
- `wages.csv`: Team wage spending for 2024-25 season  
- `standings.csv`: Final EPL standings for 2024-25 season  

## Methods
- Loaded datasets into an in-memory SQL database  
- Joined tables on `team` and `season`  
- Calculated:
  - Points per million spent  
  - Spending and performance ranks  
  - Overperformance score  
- Exported cleaned dataset (`epl_sql_scatter.csv`) for visualization

## Visualization
- **Scatter Plot:** Wage Spending (X-axis) vs Points (Y-axis)  
- **Bubble Size:** Overperformance score  
- **Color:** Points per million spent (efficiency)  
- **Trend Line:** Linear regression showing general correlation  
- **Insights:** Higher spending doesn’t always guarantee top performance; strategic investment can yield better efficiency

![Scatter Plot](Scatter_Plot.png)  

## Files
- `wages.csv` – Team wage data  
- `standings.csv` – League standings  
- `epl_sql_scatter.csv` – Merged dataset with calculated metrics  
- `EPL_SQL_Notebook.ipynb` – SQL analysis notebook  
- `Scatter_Plot.png` – Tableau scatter plot visualization  

## Insights
- Liverpool and Arsenal outperformed their wage investment  
- Some high-spending teams, like Manchester United, underperformed  
- Efficiency and strategy matter more than raw spending for league success
