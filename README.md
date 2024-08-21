# freddysaav-NBA-2023-24-Quarter-Comparison-Insights

* Compares the first three quarters with the last quarter --> fewer points in the 4th quarter are a result of slower pace (fewer possessions), not because of more defensive intensity
* Scraped the games and box score stats of the 2021/2022 season
* Engineered advanced stats from the traditional stats
* Visualized different stats and trends in specific game situations
* Made a 2-sample t-test to prove my observations
* KMeans clustering --> the top teams can elevate their game in the 4th quarter

## Code and Resources Used 
* Python Version: 3.7  
* Packages: Pandas, NumPy, Sklearn, Matplotlib, Seaborn, Selenium, sciPy 
* Data: https://www.nba.com/stats/

## Web Scraping
Scraped four tables (1st quarter, 2nd quarter, 3rd quarter, 4th quarter), each containing:
* traditional stats, e.g. Points, +/-, Assists, Rebounds, Shooting Percentages...
* Game Date
* Matchup

## Data Cleaning
For the comparison, I created new variables:
* Opponent out of Matchup
* Court (1 = home team and 0 = away team) out of Match up
* Removed season column
* Opponent stats out of the row with the right Match up
* Possessions out of FG, FGM, FTA, TOV ...
* Pace out of possessions
* Margin of victory/loss out of +/-

## EDA
I looked at the distributions of the data and combined different statistics. Below are a few highlights from the pivot tables. 

!![confusion](https://github.com/user-attachments/assets/e668cc1b-763f-4c8c-95ff-bb01f0872138)
![avg](https://github.com/user-attachments/assets/8983f069-24f9-4343-9f9a-408b208337cf)

## 2-sample t-test
I tested statistics from the first three quarters to see if they're significantly different from the 4th quarter:
* Reject H0 at the 95% confidence interval for Pace, AST, 3P%,' PTS', 'FT%
* Can't reject H0 for DEFRTG and OFFRTG at the 95% confidence interval

## KMeans Clustering (n_clusters=4)
I wanted to know the individual team performance if some teams step up in the 4th quarter:
* The top 2 in the season standings (i.e., PHOENIX SUNS, MEMPHIS GRIZZLIES) grouped in the same cluster
* Also, the bottom teams were all grouped in one cluster
* The other two groups were teams who are in the middle or don't improve much in the 4th quarter to be in the elite cluster

## Conclusion
I couldn't prove that the defence improved in the game's last quarter. The lower scoring average in the 4th is a result of fewer possessions.
Still, some teams play better in the 4th quarter, and it is not a coincidence that these are the top-ranked teams in the league. Because of that, my claim would be that the best teams have an on-switch and can play their best when it matters.
