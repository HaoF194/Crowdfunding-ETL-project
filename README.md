# Crowdfunding ETL Project

## Group Members:
- Alvin
- Kristina
- Mason
- Lisa
- Frank

## Introduction

This project involves building an ETL (Extract, Transform, Load) pipeline using Python, Pandas, and either Python dictionary methods or regular expressions. The goal is to extract and transform data to create four CSV files, and then use this data to create an Entity-Relationship Diagram (ERD) and a table schema. Finally, the CSV data will be uploaded into a PostgreSQL database.

## Programming Technique

We used a collaborative approach known as Pair Programming, where multiple team members work together at one workstation. One member, the "driver," writes and executes the code, while the others, the "observers" or "navigators," review each line of code, give feedback, and advise on debugging. Roles are frequently switched to ensure a balanced coding experience for all team members.

## Data Transformation

### 1. Category and Subcategory DataFrames
**Category DataFrame:**
- Extracted and transformed data from `crowdfunding.xlsx`.
- Columns: `category_id` (sequential from cat1 to cat9), `category` (category titles).
- Exported as `category.csv`.

**Subcategory DataFrame:**
- Extracted and transformed data from `crowdfunding.xlsx`.
- Columns: `subcategory_id` (sequential from subcat1 to subcat24), `subcategory` (subcategory titles).
- Exported as `subcategory.csv`.

### 2. Campaign DataFrame
- Extracted and transformed data from `crowdfunding.xlsx`.
- Columns: 
  - `cf_id`
  - `contact_id`
  - `company_name`
  - `description` (renamed from blurb)
  - `goal` (converted to float)
  - `pledged` (converted to float)
  - `outcome`
  - `backers_count`
  - `country`
  - `currency`
  - `launch_date` (renamed from launched_at and converted to datetime format)
  - `end_date` (renamed from deadline and converted to datetime format)
  - `category_id`
  - `subcategory_id`
- Exported as `campaign.csv`.

### 3. Contacts DataFrame
- Imported `contacts.xlsx` into a DataFrame.
- Converted each row to a dictionary.
- Extracted dictionary values and added them to a new list.
- Created a new DataFrame from this list.
- Split `name` column into `first_name` and `last_name`.
- Exported as `contacts.csv`.

## Database Creation

### Crowdfunding Database
1. **Inspect CSV Files:** Review the four CSV files created (`category.csv`, `subcategory.csv`, `campaign.csv`, `contacts.csv`).
2. **Sketch ERD:** Use QuickDBD to sketch an ERD.
3. **Create Table Schema:**
    - Specify data types, primary keys, foreign keys, and constraints for each CSV file.
    - Save the schema as `crowdfunding_db_schema.sql`.
4. **Create PostgreSQL Database:**
    - Create a new Postgres database named `crowdfunding_db`.
    - Use the schema to create the tables in the correct order.
    - Verify table creation with SELECT statements.
5. **Import CSV Data:**
    - Import each CSV file into its corresponding SQL table.
    - Verify the data with SELECT statements for each table.

## Files Overview
- `category.csv`: Contains category data.
- `subcategory.csv`: Contains subcategory data.
- `campaign.csv`: Contains campaign data.
- `contacts.csv`: Contains contacts data.
- `crowdfunding_db_schema.sql`: Contains the database schema.

## Conclusion

This project demonstrates the practical implementation of an ETL pipeline, from data extraction and transformation using Python and Pandas to the creation and population of a PostgreSQL database. The collaborative pair programming approach ensured the quality and efficiency of the code and facilitated knowledge sharing among team members.
