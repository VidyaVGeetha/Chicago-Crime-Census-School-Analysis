# Chicago Crime, Census, and School Data Analysis

This project involves data analysis using **SQL with Python** on three datasets from the city of Chicago:

- **Chicago Crime Data**
- **Chicago Census Data**
- **Chicago Public Schools Data**

The goal is to extract meaningful insights related to crime hotspots, poverty levels, school safety scores, and community hardship indices using structured queries and pandas operations.

---

## 📂 Datasets Used

- **ChicagoCrimeData.csv**: Crime incidents in Chicago.
- **ChicagoCensusData.csv**: Demographics and economic information per community area.
- **ChicagoPublicSchools.csv**: Safety and performance metrics of Chicago public schools.

---

## 🚀 Technologies Used

- Python 3
- SQLite
- SQL (via `ipython-sql`)
- Pandas
- Jupyter Notebook
- PrettyTable

---

## 📊 Key Tasks Performed

- Imported and converted CSV datasets into a SQLite database
- Ran SQL queries to:
  - Count total crimes
  - Identify crime types at schools
  - List kidnapping cases involving children
  - Analyze communities with highest poverty and hardship
  - Rank school types by safety score
  - Detect most crime-prone areas
  - Perform sub-queries for community area insights

---

## 📌 Sample Queries

```sql
-- Find the total number of crimes
SELECT COUNT(*) AS Total_Crimes FROM CHICAGO_CRIME_DATA;

-- Community area with the highest hardship index
SELECT COMMUNITY_AREA_NAME FROM CHICAGO_CENSUS_DATA
WHERE HARDSHIP_INDEX = (SELECT MAX(HARDSHIP_INDEX) FROM CHICAGO_CENSUS_DATA);

-- Crimes that occurred at schools
SELECT DISTINCT PRIMARY_TYPE FROM CHICAGO_CRIME_DATA
WHERE LOCATION_DESCRIPTION LIKE '%SCHOOL%';
