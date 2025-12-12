# Methedology

## Data Source(s)
- NBA player game-level performance data from the 2024-2025 season
- dataset includes indivudual box score statistics, game results, and opponent information
- Data was stored locally in CSV format and loaded using pandas
## Data Preparation / Cleaning
- loaded the raw CSV file into a pandas DataFrame
- checked for missing values across all columns and confirmed no missing values were present
- Grouped player game-level data by team, player, and game result (win/loss)
- Calculated average GameScore (GmSc) for players in wins and losses
- created a new metric, ('Diff') representing the difference between player GmSc in wins vs. losses
- filtered players to include only those averaging at least 25 minutes per game 
- Clump player-level 'Diff' values to the team level by averaging across all players on the team
## Assumptions
- GameScore is assumed to be one of the best statistical measures of player performance
- Difference in player performance in wins and losses is assumed to reflect the players' impact on their teams overall performance (wins vs. losses)
- Filtered players by a 25 minute minimum assumes only higher-minute players better represent a team's team's best players
- averaging GameScore differences at the team level assumes any player that qualifies contributes equally to team outcomes
- team win percentage is assumed to be an appropriate equivalent to team success.
## Limitations
- Game Score does not capture all aspects of player impact that don't show up in a box score. Such as defensive positioning, off-ball movement, player gravity, or team lineup
- Player performance difference in wins and losses may be effected by opponent strength, game situations, or team injuries and other roster changes
- This analysis does not account for playoff performance