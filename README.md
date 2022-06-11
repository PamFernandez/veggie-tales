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

The resulting data included 443 features. 
<br>
<br>
# Now I'm stuck. 
- I think that to `get_clusters` I need to have scaled data.
- I can't scale our data because it's not numeric.
- I don't think I can `get_clusters` on non numeric data.
- So I used `pd.get_dummies` to convert categorical data to numeric.
- But now I can't cluster any columns - because they are 'fruits_3_ORANGES' which has only oranges in it, and 'fruits_3_PEACHES' which has only the peaches in it.

# And. 
I also don't know what to do the Machine Learning on because there is no binary data column. Like for our homework one of the columns was IS_SUCCESSFUL - it was a 1 or 0 indicating yes or no... that was the target variable to indicate if the machine was learning succsssfully or not.
