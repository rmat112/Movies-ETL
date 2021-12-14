# ETL Extract, Transform, Load

## Project Overview
Amazing Prime is a platform for streaming movies and TV shows. They are sponsoring a hackathon, providing clean dataset to participants and asking them to predict popular pictures. To keep the datset updated we need to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. This goal was achieved in the following steps.

## 1. Write an ETL function to read three data files

Task: The dataset utilized takes in three files—Wikipedia data (JSON file), Kaggle metadata (csv file), and the MovieLens rating data (csv file).
The code to convert these files into a dataframe is as below:<br/>
[ETL_function_test.ipynb](https://github.com/rmat112/Movies-ETL/blob/main/ETL_function_test.ipynb)<br/>

#### The first 'wiki_movies_df' DataFrame:
![wiki_movies_df.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/wiki_movies_df.png)

#### The second 'kaggle_metadata' DataFrame:
![kaggle_metadat_df.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/kaggle_metadat_df.png)

#### The third 'ratings' DataFrame
![ratings.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/ratings.png)

## 2. Extract and Transform the Wikipedia Data

Task: Extracting and transforming the Wikipedia data so we can merge it with the Kaggle metadata.<br/>
The code to extract and transform data is linked below:<br/>
[ETL_clean_wiki_movies.ipynb](https://github.com/rmat112/Movies-ETL/blob/main/ETL_clean_wiki_movies.ipynb)

#### Using try-except block:
![D2_try-except.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/D2_try-except.png)

#### Clean wiki_movies_df looks like this:
![D2_wiki_movies_df.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/D2_wiki_movies_df.png)

#### Columns from wiki_movies_df DataFrame:
![D2_list.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/D2_list.png)

## 3.Extract and Transform the Kaggle Data

Task: Extracting and transforming the Kaggle metadata and MovieLens rating data, then converting the transformed data into separate DataFrames. Then, merging the Kaggle metadata DataFrame with the Wikipedia movies DataFrame to create the movies_df DataFrame. Finally, merging the MovieLens rating data DataFrame with the movies_df DataFrame to create the movies_with_ratings_df.<br/>
The code to extract and transform the data is linked below:<br/>
[ETL_clean_kaggle_data.ipynb](https://github.com/rmat112/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb)

#### Clean movies_with_ratings_df looks like this:
![D3_Step14.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/D3_Step14.png)

#### Clean movies_df looks like this:
![D3_Step15.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/D3_Step15.png)

## 4. Create the Movie Database

Task: Add the movies_df DataFrame and MovieLens rating CSV data to a SQL database.<br/>
The code to add the movies_df and ratings data is linked below:<br/>
[ETL_create_database.ipynb](https://github.com/rmat112/Movies-ETL/blob/main/ETL_create_database.ipynb)

- The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database, as determined by the movies_query.png

- The data from the MovieLens rating CSV file is added to the ratings table in the SQL database, as determined by the ratings_query.png.<br/>
![ratings_query.png](https://github.com/rmat112/Movies-ETL/blob/main/Resources/ratings_query.png)

- The elapsed time to add the data to the database is displayed in the 'ETL_create_database' python notebook referenced above.
