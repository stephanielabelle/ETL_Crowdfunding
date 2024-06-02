# ETL - Crowdfunding

## Objective
Utilize the ETL pipeline to create a PostgreSQL database with pgAdmin.

## Extraction and Transformation
Utilized jupyter notebook to extract and transform two xlsx files: [crowdfunding.xlsx](Resources/crowdfunding.xlsx) and [contacts.xlsx](Resources/contacts.xlsx).  

### Creation of Category and Subcategory DateFrames and CSVs
Two separate csv files were created containing unique category and subcategory names by ID extracted from the crowdfunding.xlsx file ([category.csv](Resources/category.csv) and [subcategory.csv](Resources/subcategory.csv)).  

### Creation of the Campaign CSV
The crowdfunding.xlsx file was extracted and transformed.  The columns "goal" and "pledged" were converted to float data type.  The "launched_at" column was renamed as "launch_date" and the UTC times were converted to datetime format.  The "deadline" column was renamed to "end_date" and the UTC times were converted to datetime format.  The "category_id" column contents were replaced with the unique identification numbers of the category DataFrame. The "subcategory_id" column contents were replaced with the unique identification numbers of the subcategory DataFrame.  Columns "staff_pick", "category", "subcategory", "spotlight", and "category & sub-category" were dropped.  The resulting DateFrame was exported as [campaign.csv](Resources/campaign.csv).

### Creation of the Contacts CSV
The contacts.xlsx file was extracted and transformed.  Columns "contact_id", "first_name", "last_name", and "email" were extracted from a JSON string.  Resulting dataframe was exported as [contacts.csv](Resources/contacts.csv).

## Loading to Crowdfunding Database
An ERD was constructed with the [QuickDBD app](https://www.quickdatabasediagrams.com/), and the schema was saved as a Postgres file named crowdfunding_db_schema with appropriate primary/foreign key and data type assignment. The crowdfunding schema along withe the 4 csv files were used to construct a PostgreSQL database named crowdfunding_db. After database creation, each table can be displayed with a SELECT statement, represented by screenshots in the [crowdfunding_db](crowdfunding_db) folder.

