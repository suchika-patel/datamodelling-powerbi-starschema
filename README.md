# datamodelling-powerbi-starschema
Turned a messy multi-table "nightmare dataset" into a clean,analysis-ready star schema in power BI.

## 📌 Project Overview

This project focuses on transforming a messy, poorly structured dataset into a clean and reliable **star-schema data model** in Power BI. The goal was to make reporting easier, improve data quality, and create a model that supports clear and trustworthy analysis.

**Tools Used:** Power BI Desktop, Power Query, DAX, and Excel/CSV files.

---

## ❌ The Problem (Before)

The original dataset had several data-modeling issues:

- Separate order tables for different years.
- Duplicate records and inconsistent values.
- Generic column names such as `Column1`, `Column2`, and so on.
- No dedicated date dimension.
- Unclear relationships between tables.
- Inconsistent keys across customer, product, and address data.
- A model that was difficult to understand and maintain.

---

## ✅ The Solution (After)

I reorganized the dataset and created a cleaner, more structured model:

- Combined yearly order tables into a single fact table.
- Renamed columns and assigned appropriate data types.
- Removed duplicate records and standardized values.
- Built dimension tables for descriptive attributes.
- Created a dedicated date table.
- Designed a star-schema model with clear relationships.
- Used active and inactive relationships where appropriate.
- Added DAX measures for reporting and analysis.
- Set up dynamic Row-Level Security (RLS) to restrict data access by user/region.

---

## 🧱 Data Model

The model follows a **star-schema approach**, separating transactional data from descriptive data.

### 📈 Fact Tables

- `FactSales`
- `FactOrder`
- `FactInventory`
- `FactPromotion`
- `FactCampaignSpend`
- `FactReturns`
- `FactDelivery`

### 📋 Dimension Tables

- `DimCustomer`
- `DimProduct`
- `DimDate`
- `DimStore`
- `DimRegion`
- `DimGeography`
- `DimCampaign`
- `DimOrderFlags`

> **Note:** Update the table names above to match the final names in your PBIX file.

---

## 🧹 Data Cleaning Steps (Power Query)

1. Appended yearly order tables into one consolidated table.
2. Promoted headers and replaced generic column names with meaningful names.
3. Corrected data types and standardized date formats.
4. Removed duplicate records where appropriate.
5. Cleaned inconsistent or missing values.
6. Standardized keys used to connect customer, product, and geography data.
7. Prepared fact and dimension tables for modeling.

---

## 🔐 Row-Level Security (RLS)

Dynamic RLS can be used to limit the data visible to each signed-in user.

### How It Works

- Identifies the signed-in user using `USERPRINCIPALNAME()`.
- Matches the user's email to a security mapping table.
- Filters the relevant region or business unit.
- Ensures users can view only the data assigned to them.

The exact role expression depends on the relationships and column names in the final model.

---

## 💡 Key Learnings

- A well-designed data model makes DAX measures easier to write and maintain.
- Star schemas help organize analytical data clearly.
- Fact-table grain should be understood before creating relationships.
- A dedicated date dimension supports time-based analysis.
- Power Query is useful for repeatable data-cleaning steps.
- Active and inactive relationships can support different analysis paths.
- Dynamic RLS helps control which records each user can access.
- Consistent naming conventions make a model easier to understand.

---

## 🛠️ How to Use
- Download the .pbix file from the powerbi/folder open it in power BI Desktop go to Model view to explore the schema.

## 👩‍💻 Author
Suchika Patel <br>
Aspiring Data Analyst | Power BI • SQL • Python <br>
💼 **LinkedIn:** https://www.linkedin.com/in/suchikapatel?utm_source=share_via&utm_content=profile&utm_medium=member_android
