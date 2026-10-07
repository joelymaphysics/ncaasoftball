# ncaasoftball
Analysis of the factors associated with winning in 2026 NCAA Division I softball using Python.
# What Drives Winning in NCAA Division I Softball?
An analysis of the relationship between offensive, pitching, and defensive performance and team success during the 2026 NCAA Division I softball season.

## Project Overview

Winning in softball requires contributions from offense, pitching, and defense, but those parts of the game may not relate to team success equally.
This project uses team-level NCAA Division I softball statistics to investigate which measures of team performance are most strongly associated with winning percentage and how offensive, pitching, and defensive performance work together in explaining team success.
The analysis was completed in Python using pandas, Matplotlib, and statsmodels.

## Questions

This project explores three main questions:
1. Which team statistics are most strongly associated with winning percentage?
2. How well can offensive, pitching, and defensive performance together explain differences in team success?
3. How does fielding performance relate to winning, particularly among teams that already field at a high level?

## Data

The dataset contains season-level statistics for 304 NCAA Division I softball teams from the 2026 season.
The original data contained separate NCAA statistical tables that required cleaning and combining into a single team-level dataset.
Winning percentage (`WIN_PCT`) was used as the primary measure of team success rather than total wins because teams often play different numbers of games throughout a season.

## Analysis

The project included:
- Data cleaning and consolidation of NCAA team statistics
- Exploratory analysis of team winning percentage
- Correlation analysis across offensive, pitching, and defensive statistics
- Selection of representative measures for each phase of the game:
  - **OBP** — offensive performance
  - **WHIP** — pitching performance
  - **Fielding Percentage** — defensive performance
- Simple and multiple linear regression
- Comparison of regression models
- Additional investigation of the relationship between fielding and winning

## Key Findings

### Pitching and offense showed the strongest relationships with winning
Among the representative statistics, WHIP had the strongest relationship with winning percentage, followed by on-base percentage.
- **WHIP:** r ≈ -0.831
- **OBP:** r ≈ 0.774
- **Fielding Percentage:** r ≈ 0.624
Lower WHIP was associated with greater team success, while higher OBP and fielding percentage were associated with greater team success.

### Combining different phases of the game explained substantially more than individual statistics
A multiple linear regression using OBP, WHIP, and fielding percentage explained approximately **87.8% of the variation in team winning percentage** within the dataset.
A model containing only OBP and WHIP explained approximately **87.4%**, meaning fielding percentage produced a relatively small increase in overall model R².
However, further analysis showed that this did not mean defensive performance was unrelated to winning.

### Strong fielding was closely associated with winning
Teams were grouped according to fielding percentage. The proportion of teams with winning records increased substantially as fielding performance increased:
- Low fielding group: **24%** had winning records
- Lower-middle group: **36%**
- Upper-middle group: **64%**
- High fielding group: **89%**
This showed a clear relationship between defensive performance and team success.

### Strong defense alone did not distinguish winners
Among teams in the highest fielding group, winning and non-winning teams had very similar fielding percentages.
The larger differences appeared elsewhere:
- Winning teams had higher average OBP.
- Winning teams had lower average WHIP.
This suggests that strong fielding is associated with winning, but defensive performance alone does not separate successful and unsuccessful teams once teams are already performing at a high defensive level.

## Conclusion

Team success in NCAA Division I softball appears to reflect performance across multiple phases of the game rather than one dominant statistic.
Pitching and offensive performance showed particularly strong relationships with winning percentage, while fielding provided an interesting additional result: strong defensive teams were much more likely to win, but among teams that already fielded well, offensive and pitching performance better distinguished winning teams from non-winning teams.
These results demonstrate why evaluating different aspects of team performance together can provide more information than considering individual statistics in isolation.

## Limitations

This analysis is based on team-level aggregate statistics from a single season and identifies associations rather than causal relationships.
The analysis does not account for factors such as strength of schedule, opponent quality, conference strength, or game-to-game variation. Fielding percentage is also an incomplete measure of defensive performance because it does not capture factors such as defensive range or difficulty of opportunities.
Future work could incorporate multiple seasons, strength-of-schedule adjustments, and more detailed game-level or defensive data.

## Tools

- Python
- pandas
- Matplotlib
- statsmodels
- Jupyter Notebook

## Repository Contents

- `softball_analysis.ipynb` — complete data cleaning, exploratory analysis, statistical modeling, and visualizations
- `data/` — cleaned team-level dataset used in the analysis
