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