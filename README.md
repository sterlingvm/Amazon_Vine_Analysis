# Amazon_Vine_Analysis - Sterling Miller

## Analysis Overview
In this project, we extract, transform, and load data on Amazon reviews for video games with reference to their specialty reviewers program: "Vine"

We want to evaluate if there is a bias in review scores based on if reviews came from the Vine program or from regular product reviews independent of the Vine Program. Of course, the evaluation is considering the fact that Vine Program reviewers are paid for their reviews, time, and service in the program.

This analysis leverages Google Colaboratory for cloud based ETL and computation.
We utilize PySpark to perform the ETL process:
    - We extract the dataset from the AWS Database (or bucket if needed), We connect to the AWS RDS instance that houses the Amazon review data.
    - We transform the data into tables that fit into previously developed SQL database structures for easy integration, loading, and manipulation 
    - We load the transformed data into the pgAdmin / Postgres database tables and can then manipulate and aanalyze the data by using SQL queries.
    - Note that in this project, we opt to manipulate the data & analyze, and calculate the data and desired metrics via DataFrames in PySpark rather than SQL queries in pgAdmin or using DataFrames in Pandas.

Our Amazon reviews (and associated data) were centered on US reviews for video games.

## Resources
- Data Source(s) Used: [Amazon Review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), [Video Games Review dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz)
- Software: Google Colab Notebook, PostgreSQL 14.2, pgAdmin 4, Amazon Web Services (AWS)

## Results
### Total number of reviews
- Vine reviews <p align="center">
![Total Vine Reviews](Resources/Images/v_r.png?raw=true "Total Vine Reviews")
</p>

<br>

- Non-Vine reviews <p align="center">
![Total non-Vine Reviews](Resources/Images/n_v_r.png?raw=true "Total non-Vine Reviews")
</p>
<br>

### Total number of 5-star reviews
- Vine reviews <p align="center">
![5-star Vine Reviews](Resources/Images/5_v_r.png?raw=true "5-star Vine Reviews")
</p>

<br>

- Non-Vine reviews <p align="center">
![5-star non-Vine Reviews](Resources/Images/5_n_v_r.png?raw=true "5-star non-Vine Reviews") 
</p>
<br>

### Percentage of 5-star reviews
- Vine reviews <p align="center">
![% of 5-star Vine Reviews](Resources/Images/p_5_v_r.png?raw=true "% of 5-star Vine Reviews") 
</p>

<br>

- Non-Vine reviews <p align="center">
![% of 5-star Vine Reviews](Resources/Images/p_5_n_v_r.png?raw=true "% of 5-star Vine Reviews") 
</p>
<br>

## Summary
Of the reviews in the Vine program, 51% were 5-stars reviews. 
Of the reviews not in the Vine Program, 39% were 5-star reviews. 
Reviewers in the Vine Program show a higher likelihood to review the product (video games in this case) more positively/favorably

## Additional Research
We could dig deeper and analyze the statistical descriptive data for the occurance of each star rating in the reviews fro both Vine and non-Vine reviews. We could map this data out and potentially even sort/analyze this data based on Natural Language Processing Models done on the raw text of the reviews themselves to determine review sentiment score / positivity-negativity