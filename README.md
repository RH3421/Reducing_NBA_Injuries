# NBA_RTP

![image](https://github.com/RH3421/NBA_RTP/blob/main/Images/KD_Achilles.png)
Kevin Durant sustains a right Achilles tendon rupture in Game 5 of the 2019 NBA Finals.

Author: [Richard Hinds](https://github.com/RH3421)

## Background
Season-ending injuries are some of the most devasting for NBA players. Not even a decade ago most of these injuries, including ACL and Achilles tendon ruptures, were nearly always career-ending. While medical technology has advanced since then, season-ending injuries are still extremely distressing for players, front office staff, and fans.

## Business Problem
Given the physical, emotional, and financial toll of these injuries, I sought to quantify risk factors and identify NBA players at high risk for season-ending injuries. 

## Data Understanding
Using a NBA injury dataset from [Kaggle](https://www.kaggle.com/datasets/ghopkins/nba-injuries-2010-2018) with more than 17,000 entries and the [NBA player stats](https://www.nba.com/stats/players/traditional/?sort=PLAYER_NAME&dir=-1&Season=2009-10&SeasonType=Regular%20Season), I created a combined dataset which links prior season stats with current season risk of season-ending injury. The hope is that such a model may be used to modify player activity to reduce risk of injury and benefit NBA players and other stakeholders.

Though false negatives are more detrimental than false positives in the current context, accuracy was chosen to be the primary metric of model evaluation along with ROC AUC and f1 score as secondary and tertiary metrics, respectively.

## Modeling
This was a binary classification study with ```out_for_season``` as the target variable. Independent variables with VIF > 10 were excluded from analysis as they demonstrated high multicollinearity. After a DummyClassifier was performed as a baseline model, a Pipeline was constructed to expedite the modeling process. Five classification models were used to analyze the data: Logistic Regression, Random Forest, XGBoost, Naive Bayes, and an ensamble model comprising the previous four models. Additionally, odds ratios for the most impactful risk factors for season-ending injury were calculated follwing the Logistic Regression model.

## Results
XGBoost achieved an accuracy of 87%, the highest of the cohort, though the ROC AUC of 50% and f1 score of 0% left much to be desired in terms of secondary and tertiary metrics. The next best performing model was Random Forest achieving an accuracy of 84%, a ROC AUC of 64%, and an f1 score of 15%. The performance of the remaining models can be seen below.

![image](https://github.com/RH3421/NBA_RTP/blob/main/Images/Performance.png) 

The 3 most impactful risk factors for season-ending injury were as follows:

  1. Players were 1.4 times more likely to sustain a season-ending injury for every personal foul they committed per game.
  2. Players were 1.37 times more likely to sustain a season-ending injury for every inch of height they had.
  3. Players were 1.29 times more likely to sustain a season-ending injury for every minute of play accumulate in a season.

## Conclusions 
To put the 3 most impactful predictors for season-ending injury into perspective, players in the study averaged 1.7 ± 0.8 personal fouls per game, have an average height of 79 ± 4 inches, and play an average of 1213 ± 857 minutes per seaon.


 


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
