# My Predicted Bracket

The Final Four that my logistic regression model predicted consisted of:
- Gonzaga University versus Duke University
- University of North Carolina (UNC) versus University of Virginia

| Final 4 Matchup         | Win Probability|
| ------------- |:--------------:|
| *Gonzaga*       | *50.70%* |
| Duke       | 49.30% |

| Final 4 Matchup         | Win Probability|
| ------------- |:--------------:|
| UNC      | 46.70% |
| *Virginia*    | *54.30%* |

In these matchups, Gonzaga was favoured to beat Duke with a 50.70% win probability. Virginia was predicted to beat UNC, 
having a 54.30% win probability.

Moving on towards the championship round, Virginia was projected to beat Gonzaga with a 52.79% win probability.

| Championship Matchup         | Win Probability|
| ------------- |:--------------:|
| Gonzaga      | 47.21% |
| *Virginia*    | *52.79%* |


Looking at the bracket overall, as of March 31st, the model correctly predicted 46 out of the 64 games played so far (71.88%).

![BracketResults](https://github.com/ClementWongTO/NCAA_Predictor/blob/master/Visualizations/Bracket_Results_331.png)
*Above: Green represents correct predictions, orange represents incorrect predictions*

# Analysis
Looking at the results, the bracket had correctly predicted at least 75% of the games in each round until the Elite 8.

||	First Four	|First Round	|Second Round	|Sweet 16	|Elite 8|
| -------------| :-------------: | :-------------: | :-------------: |:--------------:|:--------------:|
|Total Games	|4	|32	|16	|8	|4|
|Correct Predictions|	3	|24	|14	|4	|1|
|Incorrect Predictions	|1	|8	|2	|4	|3|

From here, I learned that even though a team has a higher probability of winning, the outcome is not guaranteed. With the 
probability disparities becoming much closer in later rounds, a team's likelihood of winning is less of a certainty.
While the model generates its predictions based on the sigmoidal relationships between differential game stats, intangible factors like fear, luck, and fatigue are difficult to accurately quantify in the model.

When I performed the variance analysis in Part I, we could see that the model heavily favoured features like seeding, net rating, wins, and offensive/defensive rating when performing its classifications. These factors were thus heavily weighted when determining win probability per matchup.

#### Net Rating:
![NetRating](https://github.com/ClementWongTO/NCAA_Predictor/blob/master/Visualizations/Average%20Net%20Rating.png)
This chart analyzes a teams average net rating compared to their Wolfe rating. Gonzaga and Virginia stand above the competition boasting the best average net rating across the season while also having the best Wolfe ratings. This visualization is useful in identifying teams that may be overvalued, like Villanova. Despite having a higher Wolfe rating, the team shares a similar net rating to teams that are ranked much lower, like Northeastern and Oregon.

#### Offensive and Defensive Rating:
![ORvsDR](https://github.com/ClementWongTO/NCAA_Predictor/blob/master/Visualizations/OffRtg%20and%20DefRtg%20per%20Team.png)
This chart delves further into net rating. Here we see where teams fall when it comes to their offensive and defensive ratings. Gonzaga and Virginia both boast great offenses and defenses, a factor that is probably why the model predicted them to meet in the championships. In spite of their respective star power, teams like Duke and North Carolina stand out less in these metrics, falling much closer to the average.

#### 3 point shots made per game:
![3fgm](https://github.com/ClementWongTO/NCAA_Predictor/blob/master/Visualizations/3fgm.png)
This chart visualizes the importance of 3 point field goals made. Here, we see that 3 pointers made in a game are less indicative of winning. Kentucky and NC Central both have similar 3 point numbers despite having stark differences in average win percentage.

# Future changes and implementations:

The biggest area where the model struggled was in predicting upsets. Empirically speaking, upsets should not happen if a team is more superior in its overall stats. Luck is a huge factor in college basketball that is difficult to quantify. For future reference, I may try to add a randomized luck factor where we apply a coefficient based on past upsets for specific seed matchups. Additionally, I may add more complexity to the model by adding play-by-play information to see if there are any features there that have predictive power.

