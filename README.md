# Video Game Sales Dataset Analysis
In this project, we will analyse the data and examine the correlation of features by using Scala and SQL in Databricks. Video game sales dataset has 11 columns as follows:
* Rank - Ranking of Global Sales
* Name - The games name
* Platform - Platform of the games release
* Year - Year of the game's release between 1980 and 2017
* Genre - Genre of the game
* Publisher - Publisher of the game
* NA_Sales - Sales in North America (in millions)
* EU_Sales - Sales in Europe (in millions)
* JP_Sales - Sales in Japan (in millions)
* Other_Sales - Sales in the rest of the world (in millions)
* Global_Sales - Total worldwide sales (in millions).

### Methods
To analyse the dataset first read this data by using Scala. The video game sale dataset ... "N/A" values in Year column and ... "N/A" values in the Publisher column but since Scala sees that values as a string we first change this string values to null values and then drop this values. Now we can check the correlation between different features by using SQL and to see the heatmap for the correlation of all features we will Python with the library Pandas and Seaborn. Before to do that we make preprocessing to convert string values by using Label Encoding and drop some unneccessary columns like Rank and Name.

### Data Visualization
1. Global Sales vs Year grouping in Genre

![](https://github.com/ozggnr/FinalProject_CEBD1261/blob/master/Figure_1.png)

Our first graph demonstrates how each category perfoms in terms of total Global Sales per year. From 1980 to 2010, almost all type of games show increasing Global Sales trend especially action, sports, shooter and misc. This plot also help us to understand how market volume increases in time. On the other hand, there is a dramatic drop of Global Sales after 2014, which is probably due to lack of provided dataset after 2014. Amount of data provided for 2014 and after corresponds to only 10% of whole data.

2. 20 Most Popular Games With Respect to Highest Global Sales

![](https://github.com/ozggnr/FinalProject_CEBD1261/blob/master/Figure_2.png)

We select first 20 games having the highest Global Sales and visualize their sales by grouping them with respect to different markets. It can be easily see that North America dominate the market. This plot also demonstrates how regions can have different interest on gaming.For example, while in Japan, role-playing games are on demand, North America and Europe are interested in sports games and in other contries people like action games.

3. Platform of Most Popular 100 Games

![](https://github.com/ozggnr/FinalProject_CEBD1261/blob/master/Figure_3.png)

These pie charts show percentage of total sale contribution of these games per Platform and total amount of games contributing to top 100 for each Platform. Wii owns 23% of the total sale of top 100 games, which DS follows it with 14% and X360 with 13% share. On the other hand, we can find 16% of the games contributing to top 100 has released in Platform X360, which is the highest contribution, and Wii has the second while DS has the third most games in top 100. Interestingly, even though X360 has more games in top 100 than Wii and DS, it shows less total sale for the corresponding games especially compared to Wii. This is probably because of a single game "Wii Sports" that dominated the market.

4. Publisher of Most Popular 100 Games

![](https://github.com/ozggnr/FinalProject_CEBD1261/blob/master/Figure_4.png)

It is pretty clear that Nintendo dominates the market between the years of 1980 and 2017. They share 63% of the total global sales of top 100 games. Activision follows Nintendo as second with its share of 11%, Take-two as third. This pie chart verifies that Nintendo, thanks to its product Wii, has very high global sales and therefore owns the majority of the market share.

5. Average and Total Global Sale Performances of OLD and NEW Games

![](https://github.com/ozggnr/FinalProject_CEBD1261/blob/master/Figure_5.png)

We classify Games with respect to their Year, labeled as OLD if it is released before 2007 and as NEW for 2007 and after. We determined 2007 as the Year in order to provide almost equal separation to provide balance. This bar plot indicates that NEW games have more total global sales than OLD games while OLD games have higher average global sales than the NEW ones.

6. Correlation of Features 

![](https://github.com/ozggnr/FinalProject_CEBD1261/blob/master/Heatmap.png)

Here we plot correlation of attributes via using Seaborn library in Python and it demonstrates how features correlate with each other. Platform, Genre and Publisher data were transformed into categorical data distribution (integer) through label encoding in order to calculate correlation matrix. Sales have high correlation among each other and with global sales as expected. Among them, NA and EU sales have very high correlation with global sales such as 0.94 and 0.9 respectively. This verifies our initial observation in Figure 2 about the dominancy of NA and Europe in the market. NA and EU sales almost determine the global sale. However, JP has significantly less correlation with all NA, EU and Global sales. This indicates and verifies again our previous observation that JP market favours different type of games like Role Playing - Pokemon compared to others. On the other hand, Platform, Genre and Publisher show no correlation between each other and sales. Having no particular pattern between these features and sales make sense because there are many outliers having enormous sale values like Wii Sports, Tetris, Super Mario, etc. with irregular Year pattern. One can even guess next hit will belong to Nintendo due to the fact that 63% of top 100 games belongs to it, but nevertheless average games seem drops this correlation.
