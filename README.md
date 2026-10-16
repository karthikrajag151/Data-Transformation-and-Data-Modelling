# Data-Transformation-and-Data-Modelling
# Power BI Project 1: Data Transformation & Data Modeling

## 📌 Project Overview

This project focuses on preparing, transforming, cleaning, and modeling an E-commerce sales dataset using **Microsoft Power BI and Power Query Editor**.

As an aspiring Data Analyst, I completed this project to develop practical skills in data preparation, data integration, data quality management, data aggregation, and relationship modeling. The project involves working with three related datasets to create a structured and analysis-ready data model.

The objective is to ensure data consistency, improve data quality, and establish meaningful relationships between tables for reliable business analysis.

## 🎯 Project Objectives

- Import multiple CSV datasets into Power BI.
- Transform and clean data using Power Query Editor.
- Apply appropriate data types and standardize text formatting.
- Create custom and conditional columns using business logic.
- Merge related datasets using common keys.
- Identify and handle missing values and duplicate records.
- Apply sorting and filtering to explore sales data.
- Perform grouping and aggregation for business analysis.
- Establish and validate relationships between tables.
- Build a clean and reliable data model for future reporting and visualization.

## 🗂️ Dataset Description

The project uses three datasets representing order information, order-level product details, and sales targets.

### 1. List of Orders

Contains customer and order-level information.

| Column Name | Description |
|---|---|
| Order ID | Unique identifier for an order |
| Order Date | Date on which the order was placed |
| Customer Name | Name of the customer |
| City | City associated with the order |
| State | State associated with the order |
| Category | Product category |
| Amount | Sales amount associated with the order |
| Profit | Profit earned or loss incurred |

### 2. Order Details

Contains product category and transaction details associated with orders.

| Column Name | Description |
|---|---|
| Order ID | Identifier used to connect order records |
| Category | Product category |
| Sub-Category | More specific product classification |
| Quantity | Number of units ordered |
| Amount | Amount associated with the order detail |
| Profit | Profit or loss associated with the order detail |

### 3. Sales Target

Contains monthly sales targets by product category.

| Column Name | Description |
|---|---|
| Category | Product category |
| Month of Order Date | Month associated with the sales target |
| Target | Target sales amount for the corresponding category and month |

## 🛠️ Tools and Technologies

- **Microsoft Power BI Desktop** – Data transformation and data modeling
- **Power Query Editor** – Data cleaning, transformation, merging, and aggregation
- **CSV Files** – Source datasets
- **Power BI Data Model** – Table relationships and data organization
- **GitHub** – Project documentation and portfolio management

## 🔄 Data Transformation and Preparation

### 1. Data Import

- Imported the List of Orders, Order Details, and Sales Target CSV files into Power BI.
- Opened the Power Query Editor using the Transform Data option.
- Reviewed the columns and structure of the imported datasets.

### 2. Row Limiting and Data Types

- Restricted the List of Orders table to the first 500 rows, as required by the assignment.
- Changed the Order Date column to the Date data type.
- Converted the Amount and Target columns to Fixed Decimal Number where applicable.
- Checked data types to ensure that numerical and date fields could be used correctly in calculations and analysis.

### 3. Text Formatting

- Applied Proper Case formatting to the Customer Name column.
- Standardized customer name capitalization to improve consistency and readability.

### 4. Custom Column Creation

**Location**

Merged the City and State columns to create a new column named `Location`.

Expected format:

`City, State`

This column combines geographical information into a single field for easier analysis.

**Profit Margin**

Created a custom column named `Profit Margin` using the following calculation:

`Profit Margin = Profit / Amount`

The result represents the profit margin as a percentage.

Where Amount is zero or null, appropriate handling is required to avoid division errors or misleading results. Percentage formatting can be applied to display the result clearly.

### 5. Conditional Column: Profit Status

Created a conditional column named `Profit Status` to classify records based on profitability.

| Condition | Profit Status |
|---|---|
| Profit < 0 | Loss |
| Profit = 0 | Break-Even |
| Profit > 0 | Profit |

This classification helps distinguish profitable transactions from losses and break-even transactions.

### 6. Data Merging and Integration

Merged the List of Orders and Order Details tables using the common `Order ID` column.

- Selected Order ID as the matching key.
- Applied the appropriate join type based on the assignment requirements and intended record coverage.
- Expanded the required columns from the merged table.
- Named the merged output query `Orders Data`.

This process combines customer, geographical, and order information with product-level details.

**Important:** The selected join type and resulting row count should be validated against the source data to avoid unintended record loss or duplication.

### 7. Missing Values and Duplicate Data

Reviewed all three datasets for missing values and duplicate records.

The data quality strategy included:

- Identifying null values in important columns.
- Replacing missing values only when a valid replacement could be justified.
- Removing records only when they were invalid, incomplete beyond recovery, or confirmed to be unnecessary.
- Retaining legitimate nulls where the missing information should not be assumed.
- Checking duplicate rows and investigating repeated Order IDs before removing records.

Repeated Order IDs may be valid because one order can contain multiple product or sub-category records. Therefore, duplicate handling should be based on business logic rather than removing every repeated identifier.

### 8. Sorting and Filtering

- Sorted the Orders Data table by Order Date in descending order.
- Applied a state-level filter to analyze orders from Tamil Nadu.
- Used sorting and filtering to focus on recent orders and a specific geographical region.

These operations support data exploration and validation.

### 9. Grouping and Aggregation

Duplicated the Order Details table to perform the required aggregations.

| Aggregation | Grouping Field | Calculation |
|---|---|---|
| Order Count | Order ID | Count of Order ID records |
| Average Profit | Category | Average Profit |
| Total Amount | Sub-Category | Sum of Amount |

Also duplicated the Sales Target table and grouped the data by Month of Order Date to calculate the total Target for each month.

These aggregated tables provide summarized information for further analysis.

**Note:** A count of Order ID records is not necessarily the same as a distinct count of orders. The counting method should match the intended business definition.

## 🧩 Data Modeling

Established relationships between the imported tables using the common fields.

### Relationship 1: List of Orders and Order Details

- **Common column:** Order ID
- **Purpose:** Connect customer and order information with product-level details.
- **Validation:** Confirm compatible data types, appropriate cardinality, and an active relationship.

### Relationship 2: Order Details and Sales Target

- **Common column:** Category
- **Purpose:** Connect product category information with monthly sales targets.
- **Validation:** Check whether the relationship is valid for the intended analysis and whether category values are consistent across both tables.

Used **Manage Relationships** in Power BI to review relationship settings and ensure that the relationships were active and correctly configured.

**Modeling consideration:** Order IDs can repeat in Order Details, and categories can repeat in Sales Target across different months. Relationship cardinality must be determined from the actual data. For robust monthly target comparisons, a dedicated Date or Month dimension may be needed because a category-only relationship does not uniquely identify a monthly target.

## 📊 Key Skills Demonstrated

### Data Preparation
- Importing multiple CSV files
- Changing data types
- Limiting rows
- Standardizing text values
- Creating custom columns

### Data Cleaning
- Identifying missing values
- Investigating duplicate records
- Applying data quality rules
- Validating transformed data

### Data Integration
- Merging tables using Order ID
- Expanding merged columns
- Combining order and product information

### Data Aggregation
- Counting order records
- Calculating average profit by category
- Summarizing amount by sub-category
- Aggregating monthly sales targets

### Data Modeling
- Establishing table relationships
- Validating keys and cardinality
- Managing active relationships
- Understanding category-based and order-based data connections

### Business Logic
- Calculating profit margin
- Classifying profit status
- Analyzing orders by state
- Preparing sales data for target comparisons

## 💡 Business Applications

The transformed dataset can support several business analysis activities:

- **Profitability Analysis:** Identify profitable, loss-making, and break-even transactions.
- **Product Performance:** Compare profit across categories and total amount across sub-categories.
- **Geographical Analysis:** Examine order activity by city and state.
- **Sales Target Monitoring:** Compare monthly sales performance against category-level targets when the data model supports a valid month-level comparison.
- **Data Quality Improvement:** Identify inconsistent or incomplete records before reporting.
- **Reporting Preparation:** Provide a structured foundation for Power BI dashboards and business intelligence reports.

These are potential applications of the prepared data model, not claims of measured business outcomes.

## 📁 Project Structure

```text
Power-BI-Data-Transformation-Data-Modeling/
│
├── README.md
│
├── Data/
│   ├── List of Orders.csv
│   ├── Order Details.csv
│   └── Sales Target.csv
│
├── PowerBI/
│   └── Data Transformation & Modelling.pbix
│
└── Screenshots/
    ├── Power-Query-Transformations.png
    ├── Orders-Data-Merged-Table.png
    ├── Aggregated-Tables.png
    └── Data-Model-Relationships.png
```

*The folder structure above is a recommended repository layout. Include only files and screenshots that you actually add to the repository.*

## 📸 Project Screenshots

Add screenshots from your Power BI project to document the transformations and data model.

Recommended screenshots:

1. Power Query Editor showing the imported datasets.
2. Applied Steps showing data type changes and text formatting.
3. Custom columns showing Location and Profit Margin.
4. Conditional column showing Profit Status.
5. Merged Orders Data query.
6. Grouped and aggregated tables.
7. Data Model View showing the table relationships.

These screenshots provide visual evidence of the work completed and make the repository easier to review.

## 📦 Deliverables

- Power BI Desktop file (`.pbix`) containing the imported datasets, transformation steps, merged query, aggregated tables, and data model.
- Project documentation in `README.md`.
- Screenshots documenting the transformation and modeling workflow.
- PDF documentation explaining the transformation steps and relationship design, as required by the assignment.

## 🚀 Learning Outcomes

Through this project, I developed practical knowledge of:

- Preparing raw datasets for analysis using Power Query.
- Applying data cleansing and formatting techniques.
- Creating calculated fields based on business requirements.
- Integrating related datasets through joins.
- Grouping and aggregating data for analysis.
- Evaluating null values and duplicate records using business logic.
- Establishing relationships and validating data model integrity.
- Documenting analytical workflows in a reproducible and professional manner.

## 👨‍💻 About Me

I am an aspiring Data Analyst developing my skills in data preparation, data transformation, data modeling, and business intelligence. This project is part of my learning portfolio, demonstrating my practical application of Microsoft Power BI and Power Query to prepare E-commerce data for business analysis.

I am continuously building projects to strengthen my analytical thinking, technical skills, and ability to transform raw data into meaningful business information.

---

**Project:** Power BI Assignment 1 – Data Transformation & Data Modeling  
**Domain:** E-commerce Analytics  
**Tools:** Microsoft Power BI Desktop, Power Query Editor, GitHub  
**Focus Areas:** Data Cleaning, Data Transformation, Data Integration, Aggregation, and Data Modeling
