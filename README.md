# Capstone Project
-- Song May

## Problem Statement

Soccer player transfer is a huge market in sports industry. Especially in Europe and South America where Soccer is the most famous and popular sport. Every year, there are at least two transfer windows, summer transfer window and winter transfer window. During these transfer windows, soccer clubs buy and sell their players in order to keep their teams stay competitive, improve on team strength, makeup for the weakness, and for many, simply try to gain some profits. 

The problem with these transfers is that the value of a player can be fluctuated. A good performance of a season can rise a player's value, and a bad half season could also drag the price way down. Therefore, I see the need for a method to evaluate players that is more consistent and objective. That is where data science and machine learning play their role. 

In this project, I will create a few machine learning models to rating and categorize players according to their ratings from the past performance. With this product, in hope, I could help teams such as Manchester United to be more efficient at their player transfer process and save money at the same time. 


## Data collection

Data collection has been hard at the beginning but getting easier later. I went through many soccer team and sport channel websites. I couldn't find any data that was useful for this project. The data were either about the team performance or incomprehensive player stats. 
A few weeks later, I was able to obtain a much more comprehensive dataset from Kaggle. Though with flaws, it was a still a fixer upper. The data format was clean, all the null values were concentrated instead of spreading out, and most importantly, it had more than 20 thousand player stats.

## EDA 

The EDA process is divided into two parts. The first part is to perform EDA on the overall dataset I have. 

As I mentioned above, there was no error in terms of data format. The strings and integers are where they belong. Most of the null values are concentrated in two columns 'National_Position' and 'National_Kit' which had very little to do with this project. After deleting the two columns, the remaining null value are too few to have any impact to the result no matter what method I use to clean them. So I simply dropped them. 

The next step is to systematically categorize the players according to each position. There were two columns that contains different values. One of them has the positions players preferred position, and the other has their club positions. One of the problems I faced when categorizing players is that the player's club position column has many players marked as sub as substitute and res and reserve. Those are not the proper positions. The other problem is that in the player preferred position column, there are too many positions and some has more than three preferred positions. To solve these problems, I decided that I will create a new column that will combine the best of these two columns. I replaced sub and res from the player club position with player preferred position. As for the key players, I used their club position instead of their preferre. Then the last step of this first part was to create 5 sub-datasets according to each position. They are goalkeepers, defenders, midfielders, wings, and strikers. 

The second part of EDA is to clean and figure out the features for each sub_dataset. There are some processes that are the same for all 5 datasets. I deleted the none-performance columns, using '.corr' figuring out the correlations between the label and their features. I did some research on how each position was evaluated and then combined with the correlation result, I selected 5 to 12 features for each position. From there I am ready to run models with the data I have. 

## Modeling 

With rating as my label, I chose to run simple multiple leaner regression model to kick off the process. I figured that since rating is continuous, so Regression models would be the best for predict rating. My first attempt with multiple leaner regression was successful. Due to the clean data processing and accurate feature selecting, all of my multiple leaner regression resulted above 90% without over fitting. 
I was very happy with the resultm yet I know that there always more room to improve. So after talking to my instructor I ran random forest regressor, to my suprise, all of my scores went up to avg 97%. 