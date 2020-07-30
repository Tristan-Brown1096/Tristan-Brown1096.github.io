---
layout: post
title: My first data science project
subtitle: An analysis of the history of international soccer
tags: [projects, sports, soccer]
---
For my first project with Lambda School, I chose to look at a data set containing the results of almost every international soccer game ever played. The data set starts with the game the international governing body of soccer, commonly referred to as FIFA,  recognizes as the first international game ever played, between England and Scotland all the way back in 1872, and ends with the most recent game played by the US in February of 2020, right before COVID-19 shut down the world.

For this project, my main question was: "How does playing at home affect the outcome of an international soccer game?" The motivation for this was the observation that people frequently discuss the idea of a "home field advantage" when it comes to city-based sports teams competing on a national level. From there I wondered if the same advantage exists with teams that are nationally-based competing on an international level.

# Design

For this project, I had to add a few columns of information to my dataset. In the end, I engineered 5 columns of data that ended up being of varying usefulness. The columns added that ended up providing useful information for the project were: home_win, friendly, and goal_difference. These would be used for analysis and subsetting the data set. The other columns added that ended up being less useful for this particular project, but still interesting, were: winning_team and losing_team. 

After adding my new columns, I began to subset the data. In all I made four new data sets based on the original: home, neutral, competitive, and friendly. Because of observation overlap, this gave me two pairs of DataFrames to compare: home vs neutral, and competitive vs friendly. 

# Results

For each pair of DataFrames, I looked at three things: Win Rate, Goals Scored, and Goal Difference. Goal Difference is partially derived from Goals Scored, but includes the number of goals allowed. Based on my points of analysis, I believe it can be said that even on a national team based level, home field advantage exists. I found that playing at home results in a higher win rate, more goals scored, and a much higher goal differential than playing as the designated home team of a neutral site game. The graph below shows the average goal differential for each, with bars accounting for the range of values within 95% likelihood

|![This was a surprisngly striking difference!](http://tristanbrownds.com/assets/img/Home%20vs%20Neutral%20Goal%20Differential.png)|
|:--:|
|This was a surprisingly striking difference!|

Similarly, I found that playing as the home team in a competitive environment was much better for teams than playing as the home team in a friendly game. In soccer, particularly on the international level, friendly games are a common exhibition format. These games matter marginally for the FIFA rankings, but are widely considered to be unimportant. Conversely, competitive games are ones most people are more inclined to watch, such as World Cup games or the various continental tournaments. As with the previous comparison, I found that playing in a competitive environment resulted in a higher win rate, more goals scored, and a higher goal difference. While these numbers were much more similar compared to the numbers of the previous comparison, they were all highly statistically significant (my highest p-value was in the range of 10^-8).

|![Most games resulted in less than 10 total goals!](http://tristanbrownds.com/assets/img/Goals%20Scored%20vs%20Goals%20Allowed%20Competitive%20vs%20Friendly.png)|
|:--:|
|Most games resulted in less than 10 goals|



# Final Notes

Other than my initial intended analysis, I looked into the teams that won and lost the most games. Unsurprisingly, Brazil is the winningest team in international soccer, though the rest of the top 5 may be more surprising. Following Brazil; England, Germany, Argentina, and **_Sweden_** are 2nd-5th respectively in international wins. Italy and France are 9th and 10th in wins respectively, behind **_South Korea, Mexico, and Hungary_**! For reference, Brazil has won the World Cup 5 times, Germany and Italy have won it 4 times each, Argentina and France have won twice each, England has won it once, and the other four teams have made it to the final three times total with no wins!


On the other side, the losingest team in international soccer is Finland. There aren't really any super interesting findings on this end, other than seeing Sweden as the 8th losingest team and Hungary as the 9th losingest team. This makes Sweden the 5th winningest and 8th losingest team in the long history of international soccer, while Hungary is the 8th winningest and 9th losingest team.

To view my other projects [click here](http://tristanbrownds.com/myprojects/). To view the code for this project, [click here](https://github.com/Tristan-Brown1096/DS18_Unit_1_Build_Week_Project/blob/master/unit_1_build_week_project.ipynb). To view and/or obtain the data set used for this project, [click here](https://www.kaggle.com/martj42/international-football-results-from-1872-to-2017).
