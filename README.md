# ETL - Extract, Transform and Load
## Project Overview

Raw data exists in multiple places and forms. In order to perform any kind of data analysis, this data needs to be cleaned and structured. Data pipeline process ETL – Extract, Transform, and Load is a core concept in data engineering, ensuring that data is consistent, maintains its integrity, and nontheless strives for automatization of data wrangling. Without a consistent and robust data structure, it’s nearly impossible to perform any meaningful analysis.

## Overview of the code

The goal of this analysis is to create automated pipeline that extracts, transform and loads data. This analysis consists of four parts, where each step is building up from beginning of extracting data and function testing, through transformation and cleaning process to its final step connect and load to the database. The entire process of ETL can be executed with a single call of the function ***extract_transform_load*** in the final step [ETL_create_database.ipynb](ETL_create_database.ipynb). The ETL process is broken down into four jupyter notebook files:

1.	[ETL_function_test.ipynb](ETL_function_test.ipynb)
    - Data is extracted from the website in JSON and CSV formats.
    - Data is transformed into Pandas data frames.
    - JSON file requires extra step – loading file first and then transforming into data frame.

2.	[ETL_clean_wiki_movies.ipynb](ETL_clean_wiki_movies.ipynb)
    - Function *clean_movie* combines scattered data of alternative languages into one column *alt_titles*. 
    - Its subfunction *change_column_name* organizes column names into consistent pattern.
    - In the function *extract_transform_load* the transformation process of wiki movies data begins and includes:
 
         - Python **list comprehensions**.
         - apply() and map() methods in combination with **lambda functions**.    
         - regular expressions or **RegEx**.
        
3.	[ETL_clean_kaggle_data.ipynb](ETL_clean_kaggle_data.ipynb)
    - Function *extract_transform_load* gets new tasks for cleaning Kaggle data and includes:
    
        - Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
        - Filling missing values and filtering unwanted columns.
        - Merging data frames using *pd_merge* method.
        
4.	[ETL_create_database.ipynb](ETL_create_database.ipynb)
    - Finally, the function in its final step connects to the database by **sqlalchemy** library and **to_sql** method. 
    - Complete ETL process can be executed with a single function *extract_transform_load* call.
