# Reducing NBA Injuries
![image](https://github.com/RH3421/Reducing_NBA_Injuries/blob/main/Images/DC_Achilles.jpeg)
<sub>DeMarcus Cousins sustains a left Achilles tendon rupture on January 26, 2018.</sub>

## Background
Season ending injuries are some of the most devastating for NBA players. Not even a decade ago most of these injuries, including ACL and Achilles tendon ruptures, were nearly always career-ending. While medical technology has advanced since then, season-ending injuries are still extremely distressing for players, front office staff, and fans. Given the physical, emotional, and financial toll of these injuries, I sought to quantify risk factors and develop a model to identify NBA players at high risk for season-ending injuries. 

## Streamlit App
Select a player and discover their current season predicted probability of season-ending injury using the [App](https://nba-injury-predictor.streamlit.app/). 

## Data Understanding
Using a NBA injury dataset from [Kaggle](https://www.kaggle.com/datasets/ghopkins/nba-injuries-2010-2018) with more than 17,000 entries over 9 seasons and [NBA player stats](https://www.nba.com/stats/players/traditional/?sort=PLAYER_NAME&dir=-1&Season=2009-10&SeasonType=Regular%20Season), I created a combined dataset which links prior season stats with current season injury profile. The hope is that such a model may be used to identify at-risk players so that their activity can be modified to reduce risk of injury. This would benefit both NBA players and other stakeholders.

![image](https://github.com/RH3421/NBA_RTP/blob/main/Images/Incidence_injury.png)

## Modeling
This was a binary classification study with ```out_for_season``` as the target variable. Independent variables with variance inflation factor VIF > 10 were excluded from analysis as they demonstrated high multicollinearity. A Pipeline was used to expedite the modeling process. A DummyClassifier was used to generate a baseline model. Four classification models were then used to analyze the data: LogisticRegression, RandomForestClassifier, XGBClassifier, and an ensemble model comprised of the previous three models. Additionally, odds ratios for the most impactful risk factors for season-ending injury were calculated following the LogisticRegression analysis. Though false negatives are more detrimental than false positives in the current context, accuracy was chosen to be the primary metric of model evaluation given its common usage. f1_score and ROC AUC were used as secondary metrics.

## Results
VotingClassifier achieved had the greatest accuracy, f1-score, and ROC_AUC at 84%, 32%, and 73%, respectively. This means that the model was accurate in predicting season ending injury among NBA players.

The 3 most impactful risk factors for season-ending injury were as follows:

1. Players were 1.37 times more likely to sustain a season-ending injury for every player foul they committed.
2. Players were 1.35 times more likely to sustain a season-ending injury for every cumulative minute played per season.
3. Players were 1.32 times more likely to sustain a season-ending injury for every 3-pointer they attempted per game.

Below is a visualization demonstrating the differences between the season ending injury cohort of players and the cohort that did not sustain season ending injuries. 
![image](https://github.com/RH3421/Reducing_NBA_Injuries/blob/main/Images/Median_risk_factors.png)

## Conclusions 
Players who were involved in more physical play (personal fouls per game), accumulated heavy minutes throughout the season (cumulative minutes played per season), and attempted many 3-pointers (3-pointers attempted per game) were at higher risk of season-ending injury and require strategies to mitigate risks while minimizing impact on play.

## Recommendations

Based on the analysis it is recommended that players and teams implement 3 targeted approaches to reduce risk:

1. Players averging >2 personal fouls per game should be counseled on foul avoidance strategies focused on their specific predominant foul type (blocking foul, offensive foul, etc).
2. Players averging >20 minutes of play per game should consider approved periodic rest strategies throughout the season.
3. Players attempting >2 3-pointers per game should be counseled on safe landing strategies when shooting 3-point shots.

## Limitations
There are limitations to the current project. First, the models were trained on player data from 2009 through 2019. Thus, the predictions may become less valid as we move forward in time. Next, generalizability of this model for specific injuries (ACL rupture, Achilles tendon rupture, etc.) is at best limited as season-ending injury was the classification target in this project. Last, model predictions require at least one season of NBA play. As a result, assessment of rookie NBA players is limited.

## Future Considerations
The next steps to improve upon this analysis would be to perform a matched cohort risk analysis, matching injured players with non-injured players of similar demographics to stratify risk. Next, segmenting the analysis by specific injury (ACL, Achilles tendon, etc.) would allow for more focused risk reduction recommendations. Last, extrapolating the findings and recommendations to the weekend warrior would widen the utility of this work and likely reduce risk of injury among this highly passionate cohort.

## Repository Structure
├── [Data/](https://github.com/RH3421/NBA_RTP/tree/main/Data) ---------------------------------------> Project data</br>
├── [Images/](https://github.com/RH3421/NBA_RTP/tree/main/Images) ------------------------------------> Project images</br>
├── [.gitignore](https://github.com/RH3421/NBA_RTP/blob/main/.gitignore) -----------------------------------> Project .gitignore</br>
├── [Main_Notebook.ipynb](https://github.com/RH3421/NBA_RTP/blob/main/Main_Notebook.ipynb) ----------------------> Jupyter Notebook containing finalized code</br>
├── [README.md](https://github.com/RH3421/NBA_RTP/edit/main/README.md) -------------------------------> Repository README.md (You are here now)