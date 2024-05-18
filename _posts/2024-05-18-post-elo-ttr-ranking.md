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
Every player starts with an initial rating, often set to 1000 for new players. This baseline can vary depending on the specific implementation of the ELO system.

### Expected Score Calculation
Before a match, the expected score for each player is calculated using the difference between their ratings. The expected score represents the probability of a player winning the match. It is calculated using the formula:

### Rating Adjustment
The players' ratings are then adjusted based on the match result compared to the expected score. The adjustment is calculated using the formula:

### Iterative Updates
This process is repeated for each match a player participates in, with their rating continually adjusting to reflect their current skill level.

The beauty of the ELO rating system lies in its simplicity and adaptability. It effectively balances between rewarding players for wins and recognizing the difficulty of their opponents. Over time, a player's rating becomes a reliable indicator of their skill level, making it easier to match them against opponents of similar strength and fostering a fair and competitive environment.

BUT - how precise is the German table tennis ELO system? 

# Data Analysis of (my) table tennis results
Since I play table tennis at a club for a longer time, I have a record of nearly 500 officially played matches. Using python with `pandas`, `beautifulSoup` and regular expressions, I was able to get a pandas dataframe of all my matches as follows:
![image tooltip here](/assets/images/elo_rating_initial_df.png)

The entry of the column `Predicted_Win` is set to be `True` if the win probability is greater or equal to 0.5. 





