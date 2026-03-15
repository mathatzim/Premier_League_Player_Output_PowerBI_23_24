# Premier League Player Output Dashboard (Power BI) — 2023–24

Power BI report for exploring **Premier League 2023–24** player output through:
- **Attack output**: Goals/Game vs Assists/Game scatter (with filters)
- **Defensive output**: leaderboard combining Tackles/Interceptions/Recoveries per game
- **Creative output**: leaderboard combining Through Balls, Big Chances Created, Crosses, Accurate Long Balls per game
- **Creative vs Defensive**: quadrant scatter to spot balanced contributors
- **Player profile**: percentile-based **offensive radar** + raw per-game stats
- **Player vs league average**: per-game KPIs benchmarked against league averages
- **Creative matrix**: heatmap table with a position slicer

## Open the report
1. Open **`reports/PL_Analysis.pbix`** in **Power BI Desktop**.
2. If prompted for a data source, point Power BI to **`data/pl_23-24.csv`**.
3. Click **Refresh**.

## Data
- **`data/pl_23-24.csv`** contains season-level player stats for 2023–24.
- Per-game metrics in the report are calculated using the dataset’s appearance counts.
- Column descriptions: **`docs/DATA_DICTIONARY.md`**.

## Key metrics used
- Per-game rates (e.g., Goals/Game, Assists/Game, Shots/Game, SoT/Game).
- **Creative Index** (used for sorting/leaderboards): a simple sum of selected creative per-game components.
- **League average benchmarks** are computed across all players (ignoring the selected player).
- **Radar percentiles** are shown as percent ranks per metric (0–100%) so different metrics are comparable on one chart.

Measure notes and patterns are documented in: **`docs/DAX_MEASURES.md`**.

## Project structure
- `reports/PL_Analysis.pbix` — Power BI report
- `data/pl_23-24.csv` — dataset
- `docs/` — data dictionary + DAX notes
- `outputs/screenshots/` — optional page screenshots (useful for quick preview in GitHub)

## Notes
- Some pages apply minimum-appearance filtering to reduce noise from very small samples.
- If a value looks unexpectedly low/high, check the active **filters** (Position, Appearances, etc.).

## License & attribution
If you keep this repository public, ensure you have the right to redistribute **`data/pl_23-24.csv`** and add the dataset source attribution here.
