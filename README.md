# Extract Transform Load (ETL)

## Objective

Create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables.


> **Resources:**
> *wikipedia-movies.json, movies_metadata.csv, ratings.csv, Kaggle.com, themoviedb.org, Pandas, Jupyter Notebook, PostgreSQL, pgAdmin*


## Results

Created a function test to ensure everything was in working order.  The function takes in 3 arguments which are the pathways to the data files in the "Resources" section. It reads those files into the notebook so that it can be cleaned.

#### Wikipedia file:

* eliminated all tv shows so that only movies remained.
* Created new column names to make them more in line with their respective data.
* Useed regular expressions (regex) to drop duplicate imdb_id's.
* Used list comprehensions to iterate through the columns and eliminate columns with no data.
* Used lambda and join functions to convert data in preparation for parsing.
* Created parsing function to clean columns with monetary values.
* Used 'datetime' function from Pandas library to clean date formats.

#### Kaggle file:
