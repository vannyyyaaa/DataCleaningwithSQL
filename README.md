# SQL Project: Data Cleaning for Layoffs 2022 Dataset

This project involves cleaning and standardizing the Layoffs 2022 dataset from Kaggle. The dataset includes information about layoffs in various companies globally, and the goal was to clean the data to make it usable for further analysis.

## Dataset

- **Source**: [Kaggle - Layoffs 2022 Dataset](https://www.kaggle.com/datasets/swaptr/layoffs-2022)
- **Description**: The dataset contains fields such as `company`, `industry`, `total_laid_off`, `percentage_laid_off`, `date`, `location`, `stage`, `country`, and `funds_raised_millions`.

## Objective

The objective of this project was to perform a comprehensive data cleaning process on the layoffs dataset. The key tasks included:
- Removing duplicates
- Standardizing data
- Handling null values
- Preparing the dataset for further analysis

## Steps Involved

### 1. Staging Table Creation
Created a staging table (`layoffs_staging`) to work on data cleaning while keeping the raw data intact for reference.

### 2. Duplicate Removal
Checked for duplicates using `ROW_NUMBER()` and partitioning techniques. Duplicates were identified and removed from the staging table.

### 3. Data Standardization
Standardized various columns, including:
- **Industry**: Consolidated multiple entries of the same industry (e.g., "Crypto Currency" and "CryptoCurrency" were standardized to "Crypto").
- **Country**: Corrected inconsistencies in country names (e.g., "United States." to "United States").
- **Date**: Converted string-formatted dates to the `DATE` data type.

### 4. Handling Null Values
Identified null values and handled them accordingly. For example, populated null values in the `industry` column by referencing non-null values for the same company. Kept null values in key columns like `total_laid_off` for further analysis.

### 5. Removing Unnecessary Data
Removed rows with no useful data (e.g., both `total_laid_off` and `percentage_laid_off` were null) and dropped temporary columns.

## Outcome

The dataset was successfully cleaned, standardized, and prepared for further exploratory data analysis (EDA) and modeling. The clean dataset can now be used for insightful analysis on layoffs trends.

## Technologies Used

- **SQL**: MySQL
- **Tools**: MySQL Workbench

## How to Use

1. Clone this repository.
2. Import the raw dataset into your MySQL environment.
3. Execute the SQL scripts in the `data_cleaning.sql` file to clean the data.
4. Once cleaned, you can proceed with your analysis or export the cleaned data for further processing.

## Acknowledgements

- Dataset sourced from [Kaggle](https://www.kaggle.com/datasets/swaptr/layoffs-2022).
