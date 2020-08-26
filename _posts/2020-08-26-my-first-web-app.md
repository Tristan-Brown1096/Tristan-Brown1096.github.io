---
layout: post
title: My first web app
subtitle: A model to predict the NCAA Men's Basketball Tournament
tags: [projects, sports, basketball]
---

# About the data

My data consists of various specialized basketball statistics for every NCAA Division 1 men's basketball team for the years 2010-2019.I initially 
got my data from Kaggle, but found the data provided to be lacking. Fortunately the Kaggle source had a website they cited, so in an effort to 
expand my data, I went there. The layout was pretty simple for copying the data (they didn't allow scraping, and everything I needed was easily forked)
and I worked in Excel to clean what I needed. After that step, I merged my new data with the existing data and began working on my project.

# Design

For this project I ended up building 36 models. These were mostly permutations of random forest classifiers, the xgboost classifier, and the Scikit-Learn
gradient boosting classifier, as well as a logistic regression model that was required for my class. I also tried five different splits of my data. In 
each split, I trained the models on the data from 2010-2017, validated on the data from 2018, and tested on the data from 2019. 

# Results

The first of these was just looking at all of the data, without the seed of each team. The reason for dropping the seed in this case was my choice  of target 
variable and the data I was dealing with. My target variable for this project was how well a team did in the NCAA tournament, and since the vast majority of 
teams do not make the tournament, the baseline accuracy was 80.59%, since that was the portion of teams from 2010-1017 that did not play in the NCAA tournament 
and thusdon't get seeded. With this selection of data, my most improved model gave me 86.04% accuracy, which wasn't a huge improvement over the baseline. In 
retrospect, I probably could have gotten better accuracy if I had eventually used a boosting model, but the data was too skewed for my liking, which is why I 
tried my other splits. The second split looked only at teams that did make the tournament. While this did drastically reduce the number of observations in my 
dataset, it did make the data much more practical for my web app. After cutting the data down to only the teams that did make the NCAA tournament, the baseline 
accuracy of the training data was 47.32%. Testing on this set of data, I had two models that resulted in 60.29% accuracy on the test data. My third split looked 
at the same subset of teams that made the NCAA tournament, but included their seeding. To my initial surprise, including the seeding of the teams did not improve 
model accuracy, and the majority of the models I built resulted in the same test accuracy of 60.29%. After further digging, I did find that the predictions that 
were incorrect were usually within a single round of being correct, and at most the predictions were two rounds off. A later model did get a higher accuracy score,
but was more incorrect with the incorrect predictions. My fourth split kept the seed, and dropped the number of wins the team had during the season. To my surprise, 
that did not reduce the accuracy at all, and resulted in a second model with 61.76% accuracy that was only off by two rounds at most on incorrect predictions. 
It also was accurate +- one round on 65 of the 68 teams. My final split looked only at the teams that made the tournament and dropped the seed and number of wins. 
This model was still 60.29% accurate, which was surprising to me.

# Web App

After building all of my models. I started working on a web application to predict how well a team would do in the NCAA tournament. I chose to use my model that was 
61.76% accurate and began working. It was initially more challenging than I thought it would be, but I eventually got all of the pieces together and was able to test 
it locally. I used the data from the website my dataset came from to test the predictor and included a team that it was tested on initially. It gave the same prediction 
as running it through my model in my iPython notebook, so I was satisfied with that. I also tried giving it data from 2020, since that was not in the data set due to the 
NCAA tournament not being played. 

To view my other projects [click here](http://tristanbrownds.com/myprojects/). 
To view the code for this project, [click here](https://github.com/Tristan-Brown1096/DS18_Unit_2_Build_Week_Project/blob/master/unit_2_build_week_project.ipynb).
To access the web app, [click here](https://ncaambb-predictor.herokuapp.com/)
To view and/or obtain the starting dataset used for this project, [click here](https://www.kaggle.com/andrewsundberg/college-basketball-dataset).
To access the other data used, and find data to put into the web app, [click here](https://barttorvik.com/trankpre.php).
