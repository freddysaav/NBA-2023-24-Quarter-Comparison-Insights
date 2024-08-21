  # NBA-2023-24-Quarter-Comparison-Insights

* Comparing the first three quarters with the last quarter shows that fewer points in the 4th quarter result from a slower pace (fewer possessions), rather than increased defensive intensity.
* Scraped game and box score statistics for the 2021/2022 season.
* Engineered advanced statistics from traditional stats.
* Visualized various statistics and trends in specific game situations.
* Conducted a 2-sample t-test to validate my observations.
* KMeans clustering revealed that the top teams can elevate their performance in the 4th quarter.

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
* The top 2 in the season standings (i.e., DALAS, BOSTON) grouped in the same cluster
* Also, the bottom teams were all grouped in one cluster
* The other two groups were teams who are in the middle or don't improve much in the 4th quarter to be in the elite cluster

## Conclusion
"I was unable to demonstrate that defensive intensity increases in the last quarter of the game. The lower scoring average in the 4th quarter is primarily due to a reduced number of possessions. However, certain teams consistently perform better in the 4th quarter, and it’s no coincidence that these are the league's top-ranked teams. This suggests that the best teams have the ability to elevate their performance when it matters most."
