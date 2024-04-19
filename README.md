# Project Description
__Objective__:
- Prediction of the winner of an international matches Prediction results are  "Win / Lose / Draw" or "goal difference"
- Apply the model to predict the result of FIFA world cup 2026.

__Data__: Data are assembled from multiple sources, most of them are from Kaggle, others come from FIFA website / EA games.

__Feature Engineering__: To determine who will more likely to win a match, based on my knowledge, I come up with 4 main groups of features as follows:
1. head-to-head match history between 2 teams
2. recent performance of each team (10 recent matches), aka "form"
3. bet-ratio before matches
4. squad strength (from FIFA video game)

Feature list reflects those factors.

__Lifecycle__

![](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/life_cycle.png)

# Report
Check the [Full Report](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/report.md) to gain more insight about this Project. The report contains:  
- Exploratory Data Analysis: Investigate correlations, importance of features to results, hypothesis interesting
- Methodology: How I carried out this project, which experiments I did.
- Models: baseline model, logistic regression, random forest, gradient boosting tree, ADA boost tree, Neural Network.
- Evaluation Criteria: F1, 10-fold cross validation accuracy
- Results and Conclusion

# Project Structure
1. __EDA__: Data Exploratory Analysis
2. __LE__: saved model for Label Encoder
3. __data__: completed dataset
4. __save_model__: saved Machine Learning model after training

# Data
### Data Source
The dataset are from all international matches from 2000 - 2018, results, bet odds, ranking, squad strengths
1. [FIFA World Cup 2022](https://www.kaggle.com/datasets/ashishmotwani/fifa-world-cup-2022)
2. [International match 1872 - 2024](https://www.kaggle.com/datasets/martj42/international-football-results-from-1872-to-2017)
3. [FIFA Ranking through Time](https://www.fifa.com/fifa-world-ranking/ranking-table/men/index.html)
4. [Bet Odd](https://www.kaggle.com/austro/beat-the-bookie-worldwide-football-dataset/data)
5. [Bet Odd 2](http://www.oddsportal.com)
6. [Squad Strength - Sofia](https://sofifa.com/players/top)
7. [Squad Strength - FIFA index](https://www.fifaindex.com/)



[1]: https://www.kaggle.com/ahmedelnaggar/fifa-worldcup-2018-dataset/data
[2]: https://www.kaggle.com/martj42/international-football-results-from-1872-to-2017/data
[3]: https://www.fifa.com/fifa-world-ranking/ranking-table/men/index.html
[4]: https://www.kaggle.com/austro/beat-the-bookie-worldwide-football-dataset/data
[5]: http://www.oddsportal.com
[6]: https://sofifa.com/players/top
[7]: https://www.fifaindex.com/

### Feature List
- _*difference: team1 - team2_
- _*form: performance in 10 recent matches_

| Feature Name  | Description              | Source |
|:-------------:|:------------------------:|:------:|
| team_1        | Nation Code (e.g US, NZ)      | [1] & [2] |
| team_2        | Nation Code  (e.g US, NZ)     | [1] & [2] |
| date          | Date of match yyyy - mm - dd  | [1] & [2] |
| tournament    | Friendly,EURO, AFC, FIFA WC   | [1] & [2] |
| h_win_diff    | Head2Head: win difference      |   [2]   |
| h_draw        | Head2Head: number of draw      |   [2]    |
| form_diff_goalF | Form: difference in "Goal For" |   [2]   |
| form_diff_goalA | Form: difference in "Goal Against" |   [2]    |
| form_diff_win   | Form: difference in number of win  |   [2]    |
| form_diff_draw  | Form: difference in number of draw |   [2]    |
| odd_diff_win    | Betting Odd: difference bet rate for win  | [4] & [5] |
| odd_draw        | Betting Odd: bet rate for draw            | [4] & [5] |
| game_diff_rank  | Squad Strength: difference in FIFA Rank   | [3] |
| game_diff_ovr   | Squad Strength: difference in Overall Strength  | [6] |
|game_diff_attk   | Squad Strength: difference in Attack Strength   | [6] |
|game_diff_mid    | Squad Strength: difference in Midfield Strength | [6] |
|game_diff_def    | Squad Strength: difference in Defense Strength  | [6] |
|game_diff_prestige | Squad Strength: difference in prestige        | [6] |
|game_diff_age11    | Squad Strength: difference in age of 11 starting players  | [6] |
|game_diff_ageAll   | Squad Strength: difference in age of all players          | [6] |
|game_diff_bup_speed| Squad Strength: difference in Build Up Play Speed         | [6] |
|game_diff_bup_pass | Squad Strength: difference in Build Up Play Passing       | [6] |
|game_diff_cc_pass  | Squad Strength: difference in Chance Creation Passing     | [6] |
|game_diff_cc_cross | Squad Strength: difference in Chance Creation Crossing    | [6] |
|game_diff_cc_shoot | Squad Strength: difference in Chance Creation Shooting    | [6] |
|game_diff_def_press| Squad Strength: difference in Defense Pressure            | [6] |
|game_diff_def_aggr | Squad Strength: difference in Defense Aggression          | [6] |
|game_diff_def_teamwidth  | Squad Strength: difference in Defense Team Width    | [6] |

# How to Run:

```
python experiment1-W-D-L.py
python experiment2-GoalDiff.py
python experiment3-WorldCup.py
```
### K-Nearest Neighbor (KNN)
K-Nearest Neighbor (KNN) was the second model trained. Necessary tests were applied to determine the K value and the highest accuracy value was obtained when "K=48". Next, the model was trained with cross validation. And the error rate table was extracted. Also confusion matrix and certain statistics were calculated and printed.

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/KNN1.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/KNN2.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/KNN3.png)

### Logistic Regression
The Logistic Regression Model was the third model to be trained. With cross validation, the model was trained. Also confusion matrix and certain statistics were calculated and printed.

![alt text](hhttps://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/LR1.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/LR2.png)

### Decision Tree
Decision Tree was the third model trained. 70% of the dataset was used for training and 30% for testing. The model was trained with cross validation. And the Decision Tree was written. In the model below, as mentioned earlier, "1" represents a win, "2" represents a draw, and "3" represents a loss. Finally, the confusion matrix and statistics were printed.

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/DT1.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/DT2.png)

### Random Forest
Random Forest was the last model trained and was also used as the default model in match prediction stages. First, the model was trained with cross validation. Then the model, confusion matrix and some statistics were printed.

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/RF1.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/RF2.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/RF3.png)

![alt text](https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction/blob/main/pic/KNN/RF4.png)

## Conclusion
In conclusion, our machine learning model was able to accurately predict the outcomes of World Cup matches with a high degree of accuracy. Through the use of various algorithms and techniques, we were able to analyze and process large amounts of data in order to make informed predictions about the outcomes of matches.

Overall, the results of this project demonstrate the potential of machine learning in the realm of sports prediction. By harnessing the power of data and advanced computational techniques, we were able to gain valuable insights and make accurate predictions that would have been difficult to achieve through traditional methods.

While there is always room for improvement, the success of this project highlights the potential for machine learning to revolutionize the way we approach sports analysis and prediction. As such, it is likely that we will see an increasing adoption of these techniques in the future, as more and more organizations seek to harness the power of data to gain a competitive edge.

# Reference
1. [A machine learning framework for sport result prediction](https://www.sciencedirect.com/science/article/pii/S2210832717301485)
2. [t-test definition](https://en.wikipedia.org/wiki/Student%27s_t-test)
3. [Confusion Matrix Multi-Label example](http://scikit-learn.org/stable/auto_examples/model_selection/plot_confusion_matrix.html#sphx-glr-auto-examples-model-selection-plot-confusion-matrix-py)
4. [Precision-Recall Multi-Label example](http://scikit-learn.org/stable/auto_examples/model_selection/plot_precision_recall.html#in-multi-label-settings)
5. [ROC curve example](http://scikit-learn.org/stable/auto_examples/model_selection/plot_roc.html#sphx-glr-auto-examples-model-selection-plot-roc-py)
6. [Model evaluation](http://scikit-learn.org/stable/modules/model_evaluation.html#precision-recall-f-measure-metrics)
7. [Tuning the hyper-parameters of an estimator](http://scikit-learn.org/stable/modules/grid_search.html)
8. [Validation curves](http://scikit-learn.org/stable/modules/learning_curve.html)
9. [Understand Bet odd format](https://www.pinnacle.com/en/betting-articles/educational/odds-formats-available-at-pinnacle-sports/ZWSJD9PPX69V3YXZ)
10. [EURO 2020 bet odd](https://checkbestodds.com/football-odds/archive-euro-2020)

# Task List
__Complete__
- [x] Add prediction for Matchday 2
- [x] Add feature Importance
- [x] Add feature of squad and player info
- [x] Build a web crawler for Squad each team
- [x] Build a web crawler for FIFA game player
- [x] Add a simple classification based on "bet odd".
- [x] Add feature group 1
    - [x] Add h_win_diff, h_draw
    - [x] Add rank_diff, title_diff
- [x] Add features group 2
- [x] Add features group 3
- [x] Simple EDA and a small story
- [x] Add features group 4
- [x] Prepare framework for running classifiers
- [x] Add evaluation metrics and plot
  - [x] Add accuracy, precision, recall, F1
  - [x] Add ROC curves
- [x] Build a data without player rating and squad value
- [x] Generate data and preform prediction for EURO 2016, ok now my story is more interesting
- [x] Create more data, "teamA vs teamB -> win" is equivalent to "teamB vs teamA -> lose"