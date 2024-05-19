---
title: "An Analysis of Table Tennis ELO-Ratings"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Mathematics
  - Data Analytics
  - English
---

# Introduction to ELO Ratings and Their Computation
The ELO rating system is a method for calculating the relative skill levels of players in two-player games such as chess, Go, and is also used for German table tennis player (later more). Named after its creator, Hungarian-American physicist Arpad Elo, this rating system has become the standard benchmark for evaluating player performance and predicting the outcome of matches.

## What is an ELO Rating?
An ELO rating is a numerical representation of a player's skill level. The higher the rating, the stronger the player is considered to be. The system is designed to be self-correcting, meaning that a player's rating adjusts based on their performance relative to the expected outcome of their matches. If a player consistently wins against higher-rated opponents, their rating will increase more significantly than if they win against lower-rated opponents.

## How are ELO Ratings Computed?
The computation of ELO ratings involves a few key steps:

### Initial Rating
Every player starts with an initial rating, often set to 1000 for new players. This baseline can vary depending on the specific implementation of the ELO system. In the following, we denote the elo rating as $TTR$ ("table tennis rating", see elo system for table tennis players in Germany). 

### Expected Score Calculation (Win Probability)
Before a match, the expected score for each player is calculated using the difference between their ratings. The expected score represents the probability of a player winning the match. The probability of player A winning is calculated by

$p_A = \frac{1}{1 + 10^{\frac{TTR_B - TTR_A}{150}}}$,

where $TTR_A$, $TTR_B$ denotes their elo rating. Note that the denominator (here: 150) is arbitrarily set and used for fine tuning the win probabilities. 

### Rating Adjustment
The players' ratings are then adjusted based on the match result compared to the expected score. Let $p_A$ denote the winning probability of player $A$. Then, if $A$ wins, the adjustment is $(1-p_A)\cdot K$, whereas it is $-p_A\cdot K$ for a loss. Here, $K$ denotes the adjustment constant. 

### Iterative Updates
This process is repeated for each match a player participates in, with their rating continually adjusting to reflect their current skill level.

The beauty of the ELO rating system lies in its simplicity and adaptability. It effectively balances between rewarding players for wins and recognizing the difficulty of their opponents. Over time, a player's rating becomes a reliable indicator of their skill level, making it easier to match them against opponents of similar strength and fostering a fair and competitive environment.

BUT - how precise is the German table tennis ELO system? 

# Data Analysis of (my) table tennis results
Since I play table tennis at a club for a longer time, I have a record of nearly 500 officially played matches. Using python with `pandas`, `beautifulSoup` and regular expressions, I was able to get a pandas dataframe of all my matches as follows:

|    | Game Date   | Result   |   Win Probability | Won   | Predicted_Win   |
|---:|:------------|:---------|------------------:|:------|:----------------|
|  0 | 03.02.24    | 3:0      |             0.569 | True  | True            |
|  1 | 02.12.23    | 1:3      |             0.435 | False | False           |
|  2 | 24.09.23    | 3:0      |             0.751 | True  | True            |
|  3 | 24.09.23    | 3:1      |             0.893 | True  | True            |
|  4 | 01.04.23    | 1:3      |             0.049 | False | False           |
|  5 | 01.04.23    | 1:3      |             0.237 | False | False           |
|  6 | 25.03.23    | 1:3      |             0.235 | False | False           |
|  7 | 25.03.23    | 1:3      |             0.288 | False | False           |
|  8 | 18.03.23    | 0:3      |             0.051 | False | False           |
|  9 | 18.03.23    | 3:1      |             0.576 | True  | True            |

The entry of the column `Predicted_Win` is set to be `True` if the win probability is greater or equal to 0.5. 

## Performance Measures
In order to get an indicator of the performance, we calculate the difference between the actual wins and the predicted wins. For a single match, the performance is either 1 (if the match is won against the odds), 0 (if the result is aligned with the prediction) and -1 (if the match is lost despite a predicted win). For a smoother analysis, we take a rolling window over 8 matches, which is roughly equivalent to 4 weeks during a season. 

```python
df['Performance'] = (df['Won'].astype(int) - df['Predicted_Win'].astype(int)).rolling(window=8).mean() 
```


As another performance measure, we use a rolling sum over the last 4 matches of the win probability and the actual won matches. 

```python
df['Performance'] = (df['Won'] - df['Win Probability']).rolling(window=8).mean() 
```

## How precise is the win probability?
For a first glimpse at the preciseness of the predicted win, we calculate the difference between the predicted win and the actual win. It turns out, that the prediction is not that precise as the following table shows:

| Result      | Predicted Win | Predicted Loss  |
|:------------|:---------:    |:---------------:|
| Win         | 211           | 63              |
| Loss        |134            | 65              |

