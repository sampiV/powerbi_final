

```markdown
#  NBA 2024 Analytics Dashboard — Power BI & Python Integration

##  Project Overview

This project analyzes NBA team and player performance during the 2024 season using Power BI and embedded Python scripts. It transforms raw basketball data into actionable insights to support:

- Coaching decisions and roster optimization  
- Strategic planning around player roles  
- Regional comparisons across divisions and conferences  

The dashboard allows business and technical users to explore relationships like:
- Do teams with higher PER win more?
- How does usage rate relate to scoring?
- What player roles emerge from efficiency and playmaking metrics?

---

## Types of Analytics Used

| Type              | Description |
|------------------|-------------|
| **Descriptive**  | Summary stats by team and region using KPI cards and treemaps |
| **Diagnostic**   | Scatterplots showing correlations (e.g., PER vs Wins, TOV% vs Team TOV) |
| **Predictive**   | Linear regression (Python) to model PER from MP, TS%, and USG% |
| **Prescriptive** | Recommendations for lineup strategy and player classification via KMeans |

---

##  Datasets

| Dataset | Description |
|--------|-------------|
| `nba_stats.csv` | Player-level stats (PER, USG%, TS%, AST%, TRB%, TOV%, Awards) |
| `nba_team_stats.csv` | Team-level metrics (Wins, PTS, TOV) |
| `NBA_Team_Conference_Division.csv` | Lookup table for Conference → Division → Team hierarchy |

These were cleaned using Power Query (e.g., removing "2TM" rows, fixing encoding issues like "Nikola Joki?").

---

##  Data Model

Follows a **star schema**:
- **Fact Table**: `nba_team_stats`
- **Dimensions**:
  - `nba_stats` (player stats)
  - `NBA_Team_Conference_Division` (geographic hierarchy)
  - `measures_table` (custom DAX calculations)

Snowflaking supports regional drill-downs using slicers.

---

## 🛠 Key Implementation Features

###  Power BI Visuals
- **KPI Cards** for average stats by division
- **Bubble Charts** for PER vs Wins and TOV% correlations
- **Treemaps** to visualize wins by team
- **Gauge Charts** to benchmark division win rates
- **Hierarchical Slicers** (Conference → Division)

###  Python Scripts
Embedded Python scripts power:
- **Regression Analysis**: `PER ~ MP + TS% + USG%`
- **Player Role Clustering**: Using `KMeans` on PER, USG%, AST%, TRB%, TS%

Python Libraries:  
`pandas`, `matplotlib`, `sklearn.linear_model`, `sklearn.cluster`

---

##  Analyses Summary

| Analysis | Key Question | Tool |
|---------|--------------|------|
| **1** | Clean data for consistency | Power Query + Excel |
| **2** | Predict PER | Python regression |
| **3** | PER vs Wins | Bubble chart + DAX |
| **4** | TOV vs Player TOV% | Scatter plot |
| **5** | PTS vs USG% | DAX + scatter plot |
| **6** | Wins by Region | Treemap + slicers |
| **7** | Avg PTS by Division | KPI cards |
| **9** | Divisional Scoring Comparison | Slicers + KPIs |
| **10** | Player Role Classification | KMeans clustering |

---

##  Insights & Strategic Takeaways

- Teams with **higher average PER win more games**.
- **Balanced usage** (vs star-reliant teams) leads to better scoring outcomes.
- **Turnovers correlate** with player-level TOV%, highlighting systemic issues.
- Clustering reveals **underrated contributors** who offer high efficiency without dominating usage.
- **Western Conference teams outperform Eastern** in scoring and wins.

---

##  Stakeholders

| Role | Usage |
|------|-------|
| **Analysts** | Compare team/player metrics via slicers |
| **Coaches** | Identify role players and lineup strategies |
| **Executives** | Use KPI and region-based summaries for decision-making |

---

```




