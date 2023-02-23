# More Sugar 🍬 == More Happiness ? 🧐

### Introduction

​		Our original datasets came from two csv files, "recipes" and "ratings", scraped from food.com. They include information about recipes posted on the website after 2008. In order to get the average rating per recipe, we merged these two datasets and used groupby method. Then, we assigned the average rating column back to the recipes dataset. Hence, the dataset we worked with in our project is the original recipes dataset with an additional column average rating generated from the ratings datasets. 

​	For our question, we want to explore the nutrition data of each recipe. Using this dataset, we hope to answer the following question:

> **What is the relationship between the amount of sugar and the happiness of people?**

​	By answering this question, we will be able to learn more about people’s feelings towards sweet food and figure out whether they will bring happiness to people. This will help people to determine if sweet food is what they should eat more often to keep them feeling happy. 

​	There is a total of 83782 rows in our dataset and some relevant columns to our question are "nutrition" which includes multiple nutritious values including the percentage of the daily value of sugar, and "avg_rating" which is the average rating for the recipe on a scale from 1 to 5. 



------



### Cleaning & Exploratory Data Analysis

##### **Data Cleaning**

​	In order to clean our data, we first expanded the nutritions column so that each value is in its own column thus making it easier for us to access the value we want, which is the amount of sugar in that recipe. We also changed the type of each of these nutritious values to float so we can use them to generate meaningful insights like taking the mean of them. 

​	Then we added a boolean column named "healthy" that tells us whether each recipe is healthy or not based on a standard we developed using the amount of protein and carbohydrate in that recipe. For the sake of this project, we consider a healthy recipe to be ones that have more protein and less carbohydrates. To quantify this, we use the average value of proteins and carbohydrates as the threshold to determine if values in a recipe are considered low or high.

​	We also want to determine whether people are happy with each recipe. Here we assume that a high rating means that reviewers are happy from eating the dish they cooked based on this recipe. Opposite of this means that reviewers are sad from eating the dish they cooked based on this recipe. Thus, we created a new column named happiness to determine if people are happy or sad to a recipe on average. 

​	Next, we converted the "submitted", a column that contains the date a recipe was submitted to the website, into pandas timestamp type, which allows us to extract the year out of the date and created a column named "published_year".

​	We also dealt with the outliers in the "minutes" column, which contains the time in minutes it takes to cook the recipe. We consider a recipe with a cooking time over 1 day to be unreasonable because they are outliers that do not give valuable information to our analysis, thus we will consider them as missing for the purpose of our project. We also consider a time of 0 minutes to be missing value since it is unlikely to have 0 minutes as the time needed for cooking a dish. 



##### Univariate Analysis

<iframe src="assets/hist_nsteps.html" width=800 height=600 frameBorder=0></iframe>

##### Bivariate Analysis



##### Interesting Aggregates

| published_year |   False |    True |
| -------------: | ------: | ------: |
|           2008 | 4.60127 | 4.58912 |
|           2009 | 4.62757 | 4.60903 |
|           2010 | 4.64137 | 4.63559 |
|           2011 | 4.67555 | 4.68587 |
|           2012 |  4.6695 | 4.66992 |
|           2013 | 4.64638 | 4.69144 |
|           2014 | 4.60134 | 4.62006 |
|           2015 | 4.68898 | 4.69853 |
|           2016 | 4.54036 | 4.46237 |
|           2017 | 4.47394 | 4.47876 |
|           2018 | 4.59221 | 4.65766 |

------



### Assessment of Missingness

##### NMAR Analysis



##### Missingness Dependency

- Missingness on average_rating & published year of recipe

  

- Missingness on average_rating & number of ingredients



------



### Hypothesis Testing

