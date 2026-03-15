# Key DAX measures (used by the report)

> Names may differ slightly depending on your PBIX, but the logic is the same.

## Per-game measures
```DAX
Goals/Game = DIVIDE( MAX(pl_23_24[Goals]), MAX(pl_23_24[Appearances]) )
Assists/Game = DIVIDE( MAX(pl_23_24[Assists]), MAX(pl_23_24[Appearances]) )
Shots/Game = DIVIDE( MAX(pl_23_24[Shots]), MAX(pl_23_24[Appearances]) )
SoT/Game = DIVIDE( MAX(pl_23_24[Shots on target]), MAX(pl_23_24[Appearances]) )
Big Chances Created/Game = DIVIDE( MAX(pl_23_24[Big Chances Created]), MAX(pl_23_24[Appearances]) )
Through Balls/Game = DIVIDE( MAX(pl_23_24[Through balls]), MAX(pl_23_24[Appearances]) )
Crosses/Game = DIVIDE( MAX(pl_23_24[Crosses]), MAX(pl_23_24[Appearances]) )
Acc Long Balls/Game = DIVIDE( MAX(pl_23_24[Accurate long balls]), MAX(pl_23_24[Appearances]) )
```

## League averages (ignore selected player)
```DAX
League Avg Goals/Game =
AVERAGEX(
    ALL(Players[Name]),
    CALCULATE( DIVIDE( MAX(pl_23_24[Goals]), MAX(pl_23_24[Appearances]) ) )
)
```

## Creative index (example)
```DAX
Creative Index =
[Through Balls/Game] + [Acc Long Balls/Game] + [Assists/Game] + [Big Chances Created/Game]
```

## Radar percentiles (robust, 0–1)
```DAX
Radar Percentile (Robust) =
VAR thisMetric = SELECTEDVALUE(RadarData[Metric])
VAR thisName   = SELECTEDVALUE(RadarData[Name])
VAR thisValue  =
    CALCULATE(
        MAX(RadarData[Value]),
        RadarData[Metric] = thisMetric,
        RadarData[Name] = thisName
    )
VAR baseTable =
    FILTER(
        ALL(RadarData),
        RadarData[Metric] = thisMetric
    )
VAR rankValue =
    RANKX(
        baseTable,
        CALCULATE(MAX(RadarData[Value])),
        thisValue,
        ASC,
        Dense
    )
VAR nPlayers =
    COUNTROWS(SUMMARIZE(baseTable, RadarData[Name]))
RETURN
DIVIDE(rankValue - 1, nPlayers - 1)
```
