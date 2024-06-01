# ETL - Crowdfunding

## Objective
Utilize the ETL pipeline to create a PostgreSQL database with pgAdmin.

## Extraction and Transformation
Utilized jupyter notebook to extract and transform two xlsx files: [crowdfunding.xlsx](Resources\crowdfunding.xlsx) and [contacts.xlsx](Resources\contacts.xlsx).  

### Creation of Category and Subcategory DateFrames and CSVs
Two separate csv files were created containing unique category and subcategory names by ID extracted from the crowdfunding.xlsx file ([category.csv](Resources\category.csv) and [subcategory.csv](Resources\subcategory.csv)).  

### Creation of Campaign CSVs
The crowdfunding.xlsx file was transformed.  The columns "goal" and "pledged" were converted to float data type.  The "launched_at" column was renamed as "launch_date" and the UTC times were converted to datetime format.  The "deadline" colum was renamed to "end_date" and the UTC times were converted to datetime format.  The "category_id" column contents were replaced with the unique identification numbers of the category DataFrame. The "subcategory_id" column contents were replaced with the unique identification numbers of the subcategory DataFrame.  Columns "staff_pick", "category", "subcategory", "spotlight", and "category & sub-category" were dropped.  The resulting DateFrame was exported as [campaign.csv]("Resources\campaign.csv").

