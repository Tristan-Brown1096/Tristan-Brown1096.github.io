---
layout: post
title: My Last Two Months at Lambda
subtitle: An update on my last two projects
tags: [projects, data science, group work]
---

# Unit 3 Project

For the third unit of the data science program with Lambda, you no longer get to choose your project. The project is also a group assignment.
When I did my unit three project, Lambda still had the project work cross-functionally, so I was assigned a group that consisted of both data
science students and web development students. For that project, we were assigned the task of building a website that provided a prediction of
the success or failure of a project on Kickstarter. My role in the project was quite a bit different from what I was used to, as I was in charge
of building the API that connected the model built by my seniors in the fourth unit to the web pages built by the web development team. For the
project, we were given some starter code so we could output our prediction as a JSON object. The project was deployed to Heroku and built using
FastAPI. We didn't end up completing our stretch goals we set for ourselves, so the scaffolding provided to assist in the deployment of those goals
was left with the final project, though it doesn't actually connect to anything else outside of messing with the Heroku app separately from the 
main project.

# Unit 4 Project

For my final unit in the data science track at Lambda, they made a few changes. For starters, the group consisted of only data science students. The
project was still a group assignment, but we were no longer even able to list our preffered projects and were instead assigned a project seemingly by
random. For my group, we were assigned a project to provide a recommendation for medicinal cannabis. As a Unit 4 student, I was in charge of providing
my juniors in Unit 3 with a model that would provide our recommendations. My model used natural language processing (NLP) techniques to analyze the dataset
we found and compare it with user input. There were three primary things I did with the dataset. First, I combined all of the text data from each observation
in the dataset into a new column for usage in the next steps. Next, I used the term frequency-inverse document frequency (tf-idf) vectorizor so that I could
use the text for predictions. The final step was to find the most similar strains by using the Sci-kit Learn's NearestNeighbors to provide the three closest
matches to the user input.

# Where to find the projects

My portion of the project I was assigned for my third unit at Lambda can be found [here](https://ds-ks-api-september-2020.herokuapp.com/).
To see the code for this project [click here](https://github.com/Build-Week-Kickstarter-1/DS-KickStarter/tree/master/app)
To access the final outcome of my project in Unit 4, [click here](https://medcabinetproject.herokuapp.com/)
To access the Python notebook I used to create my NLP model, [click here](https://colab.research.google.com/drive/1vBf0r45iKM6YF4Hgca5j1d5gEApqDs3_?usp=sharing)
