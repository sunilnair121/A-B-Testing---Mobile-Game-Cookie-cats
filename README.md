# A/B Testing on Cookie Cats Mobile Game

## Overview

*Cookie Cats* is a popular mobile puzzle game developed by Tactile Entertainment. The game features a classic "connect three" puzzle mechanic and includes singing cats. As players progress, they encounter gates that delay progression unless they wait or make an in-app purchase.

This project analyzes an A/B test where the first gate was moved from level 30 to level 40. The goal is to determine the impact of this change on player retention and the number of game rounds played.

## Dataset

The dataset consists of **90,189 players** who installed the game while the A/B test was running. Each player was randomly assigned to one of two groups:

- **Control Group (gate_30)**: Gate was placed at level 30.
- **Test Group (gate_40)**: Gate was placed at level 40.

### Variables:

- `userid`: Unique identifier for each player.
- `version`: Group assignment (gate_30 or gate_40).
- `sum_gamerounds`: Number of game rounds played in the first week.
- `retention_1`: Whether the player returned 1 day after installation (1 = yes, 0 = no).
- `retention_7`: Whether the player returned 7 days after installation (1 = yes, 0 = no).

## Analysis

### 1. Data Exploration

- ✔ Checked for missing values and data integrity.
- ✔ Analyzed distributions of `sum_gamerounds`, `retention_1`, and `retention_7`.
- ✔ Visualized data using histograms and boxplots.

### 2. Retention Rate Comparison

#### Retention after 1 day:

| Group    | Retention Rate |
|----------|----------------|
| gate_30  | 44.82%         |
| gate_40  | 44.44%         |
| **Difference** | -0.38%  |

#### Retention after 7 days:

| Group    | Retention Rate |
|----------|----------------|
| gate_30  | 18.61%         |
| gate_40  | 18.19%         |
| **Difference** | -0.42%  |

### 3. Game Rounds Analysis

#### Average game rounds played:

| Group    | Avg. Rounds Played |
|----------|--------------------|
| gate_30  | 51.32 rounds       |
| gate_40  | 52.46 rounds       |
| **Difference** | +1.14 rounds  |

- ✔ Used **Mann-Whitney U test** to determine statistical significance.

## Key Findings

- 📌 **Statistical Significance**: The Mann-Whitney U test resulted in a p-value of 0.0509, which is slightly above the significance threshold of 0.05. This means we fail to reject the null hypothesis, indicating no statistically significant difference in the number of game rounds played between the two groups.
  
- 📌 **Retention Analysis**: Players in **gate_30** had higher 1-day and 7-day retention rates than those in **gate_40**. This suggests that placing the gate at level 30 may be more favorable for keeping players engaged.
  
- 📌 **Game Engagement**: Although **gate_40** players played slightly more game rounds on average, the difference was not statistically significant.

## Conclusion

- 🔹 Moving the gate to level 40 had no significant impact on the number of game rounds played.
  
- 🔹 However, it slightly negatively affected player retention, with **gate_30** players showing better engagement.
  
- 🔹 These insights help game developers make informed decisions about level gating strategies while balancing monetization and player experience.
