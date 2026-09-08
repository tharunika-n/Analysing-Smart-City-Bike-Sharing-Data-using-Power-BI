# Analysing-Smart-City-Bike-Sharing-Data-using-Power-BI

## Project Overview

This project focuses on analysing Smart City Bike Sharing Data using Power BI. The dataset contains information about bike-sharing stations, their locations, capacity, availability, operational status, and city details.

The project covers data cleaning, transformation, data modelling, DAX calculations, and interactive data visualization.

## Objectives

- Import and explore the bike-sharing dataset.
- Clean and transform the data using Power Query.
- Create fact and dimension tables.
- Establish relationships between tables.
- Create DAX measures for analysis.
- Build an interactive Power BI dashboard.
- Identify useful insights from bike-sharing data.

## Dataset

The dataset contains information about bike-sharing stations across different cities.

### Main Columns

- `number` - Station identification number
- `name` - Station name
- `address` - Station address
- `position` - Station latitude and longitude
- `banking` - Banking availability
- `bonus` - Bonus station indicator
- `status` - Station operational status
- `Contract Name` - City/contract name
- `Bike Stands` - Total bike station capacity
- `Available Bike Stands` - Available bike stands
- `Available Bikes` - Currently available bikes
- `Last Update` - Last update date and time

## Data Cleaning and Transformation

The following transformations were performed using Power Query:

- Promoted the first row as headers.
- Changed columns to appropriate data types.
- Converted `Last Update` into Date/Time format.
- Created an `Update Date` column.
- Split the `position` column into `Latitude` and `Longitude`.
- Checked for duplicate records.
- Checked for missing values.
- Verified station status values.
- Verified banking and bonus fields.
- Created a unique `Station_Key`.

## Data Model

The project uses a fact and dimension table structure.

### Fact Table

- `Fact_BikeStation`

### Dimension Tables

- `Dim_City`
- `Dim_Station`
- `Dim_Date`

### Relationships

The tables are connected using:

- `Contract Name` → `Dim_City[City]`
- `Update Date` → `Dim_Date[Date]`
- `Station_Key` → `Dim_Station[Station_Key]`

## DAX Measures

### Total Stations

```DAX
Total Stations =
DISTINCTCOUNT(Fact_BikeStation[Station_Key])
