# Music Store Data Analysis Project

## Project Overview

This project involves the analysis of a **music store** database using SQL within the **pgAdmin 4** environment. The purpose of the project is to extract meaningful insights into customer behaviors, employee performance, music sales trends, and genre popularity. The dataset contains information on customers, albums, artists, tracks, invoices, and employees. By executing complex SQL queries, we aim to provide an in-depth analysis of the music store's performance and customer preferences.

## Objectives
The primary objectives of this project are to:
- Analyze customer purchase patterns.
- Evaluate employee performance and sales contributions.
- Identify the most popular music genres and artists.
- Discover key revenue-generating regions and customer demographics.
- Provide actionable insights to improve store management and sales strategies.

## Data Overview
The following tables form the core of the analysis, each providing vital data for different aspects of the music store:

### 1. **Artist**  
This table contains information about the artists whose music is available in the store.

| **ArtistID** | **Name**          |
|--------------|-------------------|
| 1            | AC/DC             |
| 2            | Accept            |
| 3            | Aerosmith         |

### 2. **Album**  
The Album table provides details of the albums, including the artist who created them.

| **AlbumID**  | **Title**                         | **ArtistID** |
|--------------|-----------------------------------|--------------|
| 1            | For Those About to Rock           | 1            |
| 2            | Balls to the Wall                 | 2            |
| 3            | Big Ones                          | 3            |

### 3. **Track**  
Tracks represent individual songs available for purchase. Each track is associated with an album and genre.

| **TrackID**  | **Name**                 | **AlbumID**  | **GenreID** | **UnitPrice** |
|--------------|--------------------------|--------------|-------------|---------------|
| 1            | For Those About to Rock   | 1            | 1           | 0.99          |
| 2            | Balls to the Wall         | 2            | 1           | 1.99          |
| 3            | Walk This Way             | 3            | 1           | 0.99          |

### 4. **Genre**  
The Genre table provides the classification of music genres.

| **GenreID**  | **Name**        |
|--------------|-----------------|
| 1            | Rock            |
| 2            | Jazz            |
| 3            | Classical       |

### 5. **Customer**  
Customers represent individuals who purchase music from the store. This table includes customer details like name and location.

| **CustomerID** | **FirstName** | **LastName** | **Country**  | **City**       |
|----------------|---------------|--------------|--------------|----------------|
| 1              | John          | Doe          | USA          | New York       |
| 2              | Jane          | Smith        | Canada       | Toronto        |
| 3              | Alice         | Johnson      | USA          | Los Angeles    |

### 6. **Invoice**  
Invoices contain purchase details, including the total amount spent by each customer.

| **InvoiceID** | **CustomerID** | **InvoiceDate** | **Total**  |
|---------------|----------------|-----------------|------------|
| 1             | 1              | 2023-01-15      | 14.99      |
| 2             | 2              | 2023-01-20      | 24.99      |
| 3             | 3              | 2023-01-25      | 9.99       |

### 7. **Employee**  
Employees are responsible for interacting with customers and selling music. This table provides information on the store employees.

| **EmployeeID** | **FirstName** | **LastName** | **Title**        |
|----------------|---------------|--------------|------------------|
| 1              | Mike          | Johnson      | Sales Support    |
| 2              | Sarah         | Davis        | Sales Support    |

## Key Insights and Analysis

### 1. **Top Customers by Purchase Total**
By analyzing the **Invoice** table, we can identify the customers with the highest purchase amounts.

| **CustomerID** | **FirstName** | **LastName** | **TotalSpent** |
|----------------|---------------|--------------|----------------|
| 2              | Jane          | Smith        | $24.99         |
| 1              | John          | Doe          | $14.99         |
| 3              | Alice         | Johnson      | $9.99          |

**Insight**: Jane Smith from Canada is the top customer, contributing the highest revenue.

### 2. **Employee Sales Performance**
We analyzed the sales handled by each employee based on the total sales attributed to them.

| **EmployeeID** | **FirstName** | **LastName** | **TotalSales** |
|----------------|---------------|--------------|----------------|
| 1              | Mike          | Johnson      | $1000          |
| 2              | Sarah         | Davis        | $1200          |

**Insight**: Sarah Davis outperforms her colleague Mike Johnson by $200 in total sales.

### 3. **Popular Music Genres**
By analyzing the **Track** and **Genre** tables, we can identify the most popular genres based on the number of tracks sold.

| **GenreID**  | **Name**        | **TracksSold** |
|--------------|-----------------|----------------|
| 1            | Rock            | 300            |
| 2            | Jazz            | 150            |

**Insight**: Rock music is the most popular genre, with 300 tracks sold.

### 4. **City-wise Revenue Distribution**
This query aggregates the total purchases made by customers from different cities.

| **City**       | **TotalRevenue** |
|----------------|------------------|
| New York       | $500             |
| Toronto        | $700             |
| Los Angeles    | $300             |

**Insight**: Toronto generates the highest revenue, followed by New York and Los Angeles.

### 5. **Album Sales Analysis**
We can also analyze which albums generate the most revenue by joining the **Album** and **Invoice** tables.

| **AlbumID** | **Title**              | **TotalSales** |
|-------------|------------------------|----------------|
| 1           | For Those About to Rock | $400           |
| 2           | Balls to the Wall       | $350           |

**Insight**: The album "For Those About to Rock" leads in sales, followed by "Balls to the Wall."

## How to Run the Project
1. **Setup Environment**: Ensure you have **pgAdmin 4** and PostgreSQL installed.
2. **Restore Database**: Use the provided SQL file to restore the music store database in pgAdmin.
3. **Run Queries**: Execute the SQL queries to retrieve the insights as shown in the analysis above.
4. **Explore Further**: You can modify the SQL queries to explore additional insights or answer custom business questions.

## Conclusion
This project provides an in-depth analysis of customer behavior, music genre popularity, employee performance, and regional sales trends. By using SQL, the music store database was effectively queried to extract actionable insights that can help in better decision-making and management of the store.

