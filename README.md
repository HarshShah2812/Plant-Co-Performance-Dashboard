# Plant Co Performance Dashboard

> This project is about building a Power BI dashboard that will show a hypothetical Plant company's financial performance across multiple years

## Overview

The aim of this project is to illustrate the process of building a Power BI dashboard, including steps such as data cleaning, modelling (DAX), building data visualisations, and formatting.

## The dataset

Here are snapshots of the tables that I worked with in this project:

Sales (Fact table)

<img width="508" alt="Screenshot 2024-07-14 at 09 41 47" src="https://github.com/user-attachments/assets/1daaedcc-af7a-4043-b6a9-662e420cc76c">

Accounts (Dimension table)

<img width="641" alt="Screenshot 2024-07-14 at 09 42 08" src="https://github.com/user-attachments/assets/a10297ba-e591-42ed-b20d-f940e81a43fa">

Products (Dimension table)

<img width="917" alt="Screenshot 2024-07-14 at 09 42 16" src="https://github.com/user-attachments/assets/ddf1220e-2313-419e-8b74-f24252a4dd5c">

## Cleaning the data

I imported the Excel file into Power BI, and decided to transform the data using the Power Query tool. What I particularly liked about this tool is that it keeps a record of all the changes made within it, and for each table, which is beneficial because you can delete certain changes if you wish. The transformations I made included renaming columns such as *latitude2* and *country2* for easier readability, removing duplicates and null values, and formatting the numeric data by adjusting the number of decimal places.

## Modelling the data

Next, I used DAX to build all the measures I needed to build the dashboard. Firstly, I created a date table called *Dim_Date*,which contains dates spanning the entirety of the time period that the sales data covers. Doing this allows for straightforward implementation of time intelligence functions in Power BI such as `TOTALYTD()` and `SAMEPERIODLASTYEAR()`, and also supports constant date filtering and grouping.

I also created a table called *Slc_Values*, which I would later use to create SWITCH measures, extremely helpful for building slicers. 

The next thing to do was build the key measures (Sales, Gross Profit, Quantity) that I would be using within both the SWITCH and Prior Year-To-Date (PYTD) measures, which I did within a *_Measures* table. Once these were built, I created the PYTD and YTD measures using the key measures already created.

Examples of both of these types of measures can be seen below:

<img width="194" alt="Screenshot 2024-07-15 at 21 34 11" src="https://github.com/user-attachments/assets/27041e75-2582-4485-83d9-0ede35d36c4c">

<img width="468" alt="Screenshot 2024-07-15 at 21 54 30" src="https://github.com/user-attachments/assets/3e0dc802-854f-4cd4-80eb-bac5737c2a93">

I then built SWITCH measures for both the YTD and PYTD data. Screenshots of them can be seen below:

<img width="316" alt="Screenshot 2024-07-15 at 22 05 26" src="https://github.com/user-attachments/assets/06d62318-1965-4262-8e5d-f3d77e5780db">

<img width="579" alt="Screenshot 2024-07-16 at 22 57 38" src="https://github.com/user-attachments/assets/c5583d65-ad11-48ab-8ccc-eee3ad54bc1f">

I also created a measure called *YTD vs PYTD*, which subtracts the PYTD measure from the YTD measure in question e.g. YTD_Sales - PYTD_Sales.

One more thing I did was establish the relationships between the different tables inside *Model View*. The result can be seen below (1 represents One and * represents Many):

<img width="579" alt="Screenshot 2024-07-16 at 22 45 21" src="https://github.com/user-attachments/assets/059bc9b7-24a6-41f8-a966-305295e60e81">