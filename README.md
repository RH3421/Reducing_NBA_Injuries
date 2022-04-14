# NBA_RTP

![image](https://github.com/RH3421/NBA_RTP/blob/main/Images/KD_Achilles.png)
Kevin Durant sustains a right Achilles tendon rupture in Game 5 of the 2019 NBA Finals.

Author:  [Richard Hinds](https://github.com/RH3421)

## Background
Season-ending injuries are some of the most devasting for NBA players. Not even a decade ago, most of these injuries, including ACL and Achilles tendon ruptures were nearly always career-ending. While medical technology has advanced since then, season-ending injuries are still extremely distressing for players, front office staff, and fans.

## Business Problem
Given the physical, emotional, and financial toll of these injuries, I sought to quantify risk factors and identify NBA players at high risk for season-ending injuries. 

## Data Understanding
Using a NBA injury dataset from [Kaggle](https://www.kaggle.com/datasets/ghopkins/nba-injuries-2010-2018) with more than 17,000 entries and [NBA player stats](https://www.nba.com/stats/players/traditional/?sort=PLAYER_NAME&dir=-1&Season=2009-10&SeasonType=Regular%20Season) to create a combined dataset, I was linked prior season stats with current season risk of season-ending injury. The hope is that such information may be used to modify player activity to reduce risk of injury and benefit NBA players and other stakeholders.

Given the relatively low incidence of season-ending injuries, f1_score was determined to be the primary metric of model evaluation along with ROC AUC as a secondary metric.

## Modeling


## Results
Best model f1 score

The 3 most impactful predictors of season-ending injury were as follows:

  1. 
  2. 
  3. 

## Conclusions 



## Recommendations

Based on the analysis it is recommended that players implement 3 targeted approaches to reduce risk:

  1.  
  2. 
  3. 

## Future Considerations
Performing a matched cohort study would address the target feature imbalance and allow for a more focused analysis.

## For More Information
View the full model via the [Jupyter Notebook](https://github.com/RH3421/Project-4/blob/main/Main_Notebook.ipynb).

## Repository Structure
