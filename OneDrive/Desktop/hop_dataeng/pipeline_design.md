 # Github Repositories Pipeline Design

 ## Bronze Layer

 ### What data will you collect?
 - Repositories from 50 Github users
 - For each repository: owner, name, language, created_at, updated_at, description, stargazers_count

 ### How much data?
 - 50 Users
 - Each users has to have ~10-30 repositories (estimated)
 - Total will be ~1000 - 1500 repositories

 ### What's the schema?
 - Owner login (string) - username of repository owner
 - Repository name (string)
 - Language (string, can be null)
 - Created date (date)
 - Updated date (date)
 - Description (string, can be null)
 - Stars count (number)

 ### What can go wrong?
 - API might be slow
 - Some fields might be null (language, description)
 - Rate limiting (github limit requests)
 - Network errors

 ### How will you handle these issues?
 - Add retry logic (try again if it fails)
 - Add delays between requests
 - Handle null values gracefully

 ## Silver Layer

 ### What validations do you need?
 - Remove duplicate repositories
 - Remove rows with null names
 - Remove rows with null owner
 - Standardize date formats

 ### What transformations?
 - Extract owner_login from nested owner dictionary
 - Clean language names
 - Remove special characters from descriptions
 - Convert dates to standard formats

 ### What quality flags?
 - Mark repositories with missing language
 - Mark repositories with missing description

 ## Gold Layer
 
 ### What business questions does this answer?
 - What are the most popular programming languages?
 - Which users have the most repositories?
 - What's the trend in repository creation over time?

 ### What aggregations/features?
 - Count repositories by language
 - Count repositories by user
 - Average stars by language

 ### What tables will you create?
 - Top languages by popularity
 - Top users by repository count
 - Repositories by creation date
 

