# Premier League Player Output Dashboard (Power BI) — 2023–24

Interactive Power BI dashboard for **Premier League 2023–24** player output and profiles.
It includes:
- attacking output scatter (Goals/Game vs Assists/Game)
- defensive output leaderboard (Tackles/Interceptions/Recoveries per game)
- creative output leaderboard (Through balls / Big chances created / Crosses / Accurate long balls per game)
- creative vs defensive quadrant view
- **player profile radar** (percentile-based) + raw stats
- player vs league-average benchmarking (per-game KPIs)
- creative matrix with position filter

> **Note:** The dataset in this repo contains season totals; per-game metrics are computed inside Power BI as totals divided by appearances.

## Files
- `reports/PL_Analysis.pbix` — Power BI report
- `data/pl_23-24.csv` — dataset (season totals)
- `docs/DATA_DICTIONARY.md` — columns + notes
- `docs/DAX_MEASURES.md` — key measures used in the report
- `outputs/screenshots/` — add exported dashboard screenshots here (recommended for GitHub)

## How to open & refresh
1. Download the repo and open `reports/PL_Analysis.pbix` in Power BI Desktop.
2. If Power BI asks for the data source, point it to `data/pl_23-24.csv`.
3. Click **Refresh**.

## Recommended screenshots for GitHub
Power BI files don’t render on GitHub, so add 3–6 images:
- Attack Output scatter
- Defensive Output leaderboard
- Creative Output leaderboard
- Player Offensive Radar
- Player vs League Average KPIs

Export: **File → Export → PNG** (or take clean screenshots) and place them in `outputs/screenshots/`, then embed them in this README.

## License & data
This repo contains a CSV dataset file (`data/pl_23-24.csv`). If you plan to keep the repo public, make sure you have the right to redistribute the dataset and add an appropriate attribution/source note in the README.
