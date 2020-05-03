# NBA 4th Quarter Analysis: Project Overview
* compares the first three quarters with the last quarter --> less points in the 4th quarter are a result of slower pace (less possessions), not because of more defensive intensity
* scraped the games and box score stats of the 2019/2020 season (until the hiatus at the 11th March 2020, because of Covid-19)
* Engineered advanced stats from the traditional stats
* visualized different stats and trends in specific game situations
* made a 2-sample t-test to prove my observations
* KMeans clustering --> the top teams can elevate their game in the 4th quarter

## Code and Resources Used 
** Python Version:** 3.7  
** Packages:** pandas, numpy, sklearn, matplotlib, seaborn, selenium, sciPy 
** Data: https://stats.nba.com/
** structure and formatting of the project: https://github.com/PlayingNumbers/ds_salary_proj/blob/master/README.md

## Web Scraping
scraped 4 tables (1st quarter, 2nd quarter, 3rd quarter, 4th quarter), each contain:
* traditional stats, e.g. Points, +/-, Assists, Rebounds, Shooting Percentages...
* Game Date
* Matchup

## Data Cleaning
For the comparison I created new variables:
* opponent out of Match up
* Court (1 = home team and 0 = away team) out of Match up
* removed season column
* opponent stats out of the row witch the right match up
* possessions out of FG, FGM, FTA, TOV ...
* pace out of possessions
* margin of victory/loss out of +/-

## EDA
I looked at the distributions of the data and combined diffrent statistics. Below are a few highlights from the pivot tables. 

![alt text](https://github.com/Schlon24/NBA_4thQuarter/blob/master/score_matrix.png "relation: lead in 3rd quarter and margin of victory")
![alt text](https://github.com/Schlon24/NBA_4thQuarter/blob/master/RTG_plot.png)

## 2-sample t-test
I tested statistics from the first three quarters, if they´re significant different from the 4th quarter:
* reject H0 at the 95% confidence interval for Pace, AST, 3P%,'PTS','FT%
* can´t reject H0 for DEFRTG and OFFRTG at the 95% confidence interval

## KMeans Clustering (n_clusters=4)
I wanted to know the individual team performance, if some teams step up in the 4th quarter:
*the actual top 3 in the standings (Bucks, Lakers, Clippers) grouped in the same cluster + the contenders in the west (Thunder, Mavericks)
*also, the bottom teams were all grouped in one cluster
*the other two grouped was teams, who are in the middle or don´t improve much in the 4th quarter to be in the elite cluster

## Conclusion
i couldn´t prove, that the defense improved in the last quarter of the game. The lower scoring average in the 4th is a result of less possessions.
Still they´re some teams, who play better in the 4th quarter and it is not a coincidence that this are the top ranked teams of the league. Because of that my claim would be, that the best teams have an on-switch and can play their best, when it matters.
