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


# Project Structure
1. __EDA__: Data Exploratory Analysis
2. __DM__: Data Modeling (KNN, Decision Trees)
3. __Visualisation__: Visualisation
4. __save_model__: saved Machine Learning model after training

## Prerequisites
List the prerequisites or dependencies users need to install and run your project. Include links to relevant documentation or resources.

Python (>=3.6)
Streamlit
Pandas
Pickle
Scipy

[1]: https://www.kaggle.com/ahmedelnaggar/fifa-worldcup-2018-dataset/data
[2]: https://www.kaggle.com/martj42/international-football-results-from-1872-to-2017/data
[3]: https://www.fifa.com/fifa-world-ranking/ranking-table/men/index.html
[4]: https://www.kaggle.com/austro/beat-the-bookie-worldwide-football-dataset/data
[5]: http://www.oddsportal.com
[6]: https://sofifa.com/players/top
[7]: https://www.fifaindex.com/

## Installation 

Provide step-by-step instructions for users to install your project.

git clone https://github.com/AhmetA97/FIFA_World_Cup_2026_Prediction

## Usage

1. Run the Streamlit app:
``
streamlit run app.py
``
2. Open the provided URL in your web browser.

3. Adjust input features in the sidebar to predict customer churn.

4. Click the "Predict" button to see the prediction outcome.

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





