# Extract Transform Load (ETL)

## Objective

Create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables.


> **Resources:**
> *wikipedia-movies.json, movies_metadata.csv, ratings.csv, Kaggle.com, themoviedb.org, Pandas, Jupyter Notebook, PostgreSQL, pgAdmin*


## Results

Created a function test to ensure everything was in working order.  The function takes in 3 arguments which are the pathways to the data files in the "Resources" section. It reads those files into the notebook so that it can be cleaned.

#### Wikipedia file:

* Eliminated all tv shows so that only movies remained.
* Created new column names to make them more in line with their respective data.
* Useed regular expressions (regex) to drop duplicate imdb_ID's.
* Used list comprehensions to iterate through the columns and eliminate columns with no data.
* Used lambda and join functions to convert data in preparation for parsing.
* Created parsing function to clean columns with monetary values.
* Used 'datetime' function from Pandas library to clean date formats.

#### Kaggle file:

* Merged the cleaned wikipedia file with kaggle file on the imdb_ID shared key.
* Dropped unnecessary columns from the wikipedia data that didn't help fill in missing Kaggle data.
* Filled missing kaggle data with data from wikipedia columns then dropped the remaining redundant columns.
* Filtered the dataframe for the specific columns to rename for another merge.

#### Ratings file:

* Grouped the data by the movie ID and rating to create a dataframe that gave the count of each rating a movie received
* Merged the ratings with the merged data above.
* Created a connection to the PostgreSQL database.
* Nested a "for loop" in the function to upload the data to the SQL database.


## Summary

As of the time of this project the movies, the movies table in the SQL database contains 6052 rows and the ratings table contains 26,024,289 rows.

> **Movies Query**
![movies_query](https://user-images.githubusercontent.com/108758105/191391195-6273d3c9-96d5-4f7a-adf4-d46795622582.png)


> **Ratings Query**\
![ratings_query](https://user-images.githubusercontent.com/108758105/191391187-d2edaa7b-f30f-4d4a-9203-1fd8202e46ff.png)



