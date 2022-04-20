# Reducing NBA Injuries
![image](https://github.com/RH3421/Reducing_NBA_Injuries/blob/main/Images/DC_Achilles.jpeg)
<sub>DeMarcus Cousins sustains a left Achilles tendon rupture on January 26, 2018.</sub>

Author: [Richard Hinds](https://github.com/RH3421)

## Background
Season ending injuries are some of the most devastating for NBA players. Not even a decade ago most of these injuries, including ACL and Achilles tendon ruptures, were nearly always career-ending. While medical technology has advanced since then, season-ending injuries are still extremely distressing for players, front office staff, and fans. Given the physical, emotional, and financial toll of these injuries, I sought to quantify risk factors and develop a model to identify NBA players at high risk for season-ending injuries. 

## Data Understanding
Using a NBA injury dataset from [Kaggle](https://www.kaggle.com/datasets/ghopkins/nba-injuries-2010-2018) with more than 17,000 entries over 9 seasons and [NBA player stats](https://www.nba.com/stats/players/traditional/?sort=PLAYER_NAME&dir=-1&Season=2009-10&SeasonType=Regular%20Season), I created a combined dataset which links prior season stats with current season risk of season-ending injury. The hope is that such a model may be used to identify at-risk players so that their activity can be modified to reduce risk of injury. This would benefit both NBA players and other stakeholders.

![image](https://github.com/RH3421/NBA_RTP/blob/main/Images/Incidence_injury.png)

## Modeling
This was a binary classification study with ```out_for_season``` as the target variable. Independent variables with variable inflation factor (VIF) > 10 were excluded from analysis as they demonstrated high multicollinearity. After a DummyClassifier was performed as a baseline model, a Pipeline was constructed to expedite the modeling process. Four classification models were used to analyze the data: Logistic Regression, Random Forest, XGBoost, and an ensemble model comprised of the previous three models. Additionally, odds ratios for the most impactful risk factors for season-ending injury were calculated following the Logistic Regression model. Though false negatives are more detrimental than false positives in the current context, accuracy was chosen to be the primary metric of model evaluation along with ROC AUC and f1_score as secondary and tertiary metrics, respectively.

## Results
Both RandomForest and XGBoost achieved an accuracy of 90% with a ROC AUC of 96% and f1_score of 90%. This means that our model was very effective in predicting season ending injury among NBA players. The performance of all models can be seen below.

![image](https://github.com/RH3421/Reducing_NBA_Injuries/blob/main/Images/Model_Comparison.png) 

The 3 most impactful risk factors for season-ending injury were as follows:

1. Players were 1.57 times more likely to sustain a season-ending injury for every personal foul they committed per game.
2. Players were 1.23 times more likely to sustain a season-ending injury for every pound they weighed.
3. Players were 1.2 times more likely to sustain a season-ending injury for every percent of 3 point shooting accuracy they demonstrated.

## Conclusions 
To put the 3 most impactful risk factors for season-ending injury into perspective, players in the study averaged 1.7 ± 0.8 personal fouls per game, had an average weight of 222 ± 27 pounds, and had an average 3 point field goal percentage of 25 ± 17%. Below is a comparison of the mean values for the 3 most impactful risk factors between those who sustained season ending injuries and those who did not.

![image](https://github.com/RH3421/Reducing_NBA_Injuries/blob/main/Images/Mean_risk_factors.png)

It seems that players involved in more physical play (personal fouls per game), who weighed more (weight), and who shot 3 pointers well (3 point field goal percentage) are at high risk and require strategies to mitigate risks while minimizing impact on play.

## Recommendations

Based on the analysis it is recommended that players implement 3 targeted approaches to reduce risk:

1. Players averaging >2 personal fouls per game should be counseled on foul avoidance strategies focused on their specific predominant foul type (blocking foul, illegal screen, etc).
2. Players weighing >223 pounds should be on an injury prevention training plan and closely monitored for signs of injury.
3. Players who have a 3 point shooting percentage >28% should be counseled on safe landing strategies when shooting 3 point shots.

## Future Considerations
The next steps to improve upon this analysis would be to perform a matched cohort study, matching injured and non-injured players with similar demographic data to reduce confounding. Along with that, segmenting the analysis by specific injury (ACL, Achilles tendon, etc.) would allow for more focused risk reduction recommendations. Last, extrapolating the findings and recommendations to the weekend warrior would widen the utility of this work and likely reduce risk of injury among this highly passionate cohort.

## Repository Structure
├── [Data/](https://github.com/RH3421/NBA_RTP/tree/main/Data) ---------------------------------------> Project data</br>
├── [Images/](https://github.com/RH3421/NBA_RTP/tree/main/Images) ------------------------------------> Project images</br>
├── [.gitignore](https://github.com/RH3421/NBA_RTP/blob/main/.gitignore) -----------------------------------> Project .gitignore</br>
├── [Main_Notebook.ipynb](https://github.com/RH3421/NBA_RTP/blob/main/Main_Notebook.ipynb) ----------------------> Jupyter Notebook containing finalized code</br>
├── [Presentation.pdf](https://github.com/RH3421/NBA_RTP/blob/main/Presentation.pdf) ---------------------------> Presentation PDF</br>
├── [README.md](https://github.com/RH3421/NBA_RTP/edit/main/README.md) -------------------------------> Repo README.md (You are here now)
