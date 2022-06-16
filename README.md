### 23. project-4 
# Veggie Tales

## Overview
### The goal of this project is to see if we can use machine learning to predict what vegetables a person may like given their current vegetable preference.
----------------------------
----------------------------

## Process
We created a survey that we asked our families, friends, and collegues to fill out regarding their vegetable eating habits and which vegetables they prefered. We also asked questions regarding their favorite fruits and TV shows thinking that we may also be able to use machine learning to see if we could find any preferances linking these variables to vegetable preferances.

We were able to get more than 160 responses to our survey giving us a great data set to work with.

The google form was able to put all our data into an Excel file and we imported the excel file directly into Pandas. This file contained 161 rows and 17 columns of data collected from the survey.

PREPROCESSING<br>
We preprocessed the data by:
* renaming the columns
* splitting the data on semi-colons or commas as needed to get each response into it's own column
* dropping any extra responses beyond the quantity requested
* renaming the new columns with individual responses in them
* adding all these new individual dataframes back into our main dataframe
* dropping all non-beneficial columns
* capitalizing all the values in the database
* doing lots of manual cleaning to make sure values are uniform
* binning all rare categorical values in the 'fruits_1', 'fruits_2', and 'fruits_3' into a new value called "other"
* transforming the 'gender' column to be numeric
* using `pd.get_dummies()` to convert categorical data to numeric,

The resulting data included 637 features. 

MAKE CLUSTERS<br>
We attempted to make clusters, but the plots were unremarkable because we had used `pd.get_dummies()` to convert our data.

COLLABORATIVE FILTERING<br>
We then created a list of all the vegetables that were in the to_eat_1, to_eat_2, to_eat_3, to_eat_4, and to_eat_5. And created a unique veg_id for each vegetable.

We then prepaerd the data for collaborative filtering by:
* creating a data frame that included only the user 'id', the 'veg_id', and a value of '1' to indicate that the user likes this vegetable
* creating a data frram that indicated which vegetables the user did NOT like and gave it a value of '0'
* Using random generator to select an equal number of rows that have 0

So in the end we had a dataset that had three columns - user 'id', 'veg_id' and 'likes' and 1750 rows where there were 875 rows with 1s (indicating like) and 875 rows with 0s (indicating not on their list of likes).

We then applied the collaborative filtering to this dataset and created the visualizations that resulted in a tableau dashboard that can be found here: https://public.tableau.com/app/profile/emma.dublin/viz/VeggieTalesProject4/DEMOGRAPHICS?publish=yes

