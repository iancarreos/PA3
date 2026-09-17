# PA3
# ECE2112 Experiment 3

**Name:** Carreos, Christian Benedict R. **Section:** 2ECE-D

## Description

This experiment uses **Pandas** in Python to work with a car dataset. It includes selecting rows and columns, finding specific car models, and filtering multiple records based on their model names.

## Part A – Positional and Label-Based Slicing


The `cars.csv` file is loaded using Pandas:

**import pandas as pd**

**cars = pd.read_csv('cars.csv')**

The shape and column names of the dataset are displayed using:

**cars.shape**

**cars.columns**

The dataset has **32 rows** and **12 columns**.

Positional slicing is used to get rows 6 through 10:

**cars_6_to_10 = cars.iloc[5:10]**

The `iloc` function selects rows based on their position. Since Python starts counting at 0, position 5 represents the 6th row.

Specific columns are then selected using:

**cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]**

This keeps only the Model, mpg, cyl, hp, and gear columns.

## Part B – Model Lookup

Boolean indexing is used to find specific car models without using their row numbers.

Toyota Corolla is found using:

**toyota = cars[cars["Model"] == 'Toyota Corolla']**

The complete row for Toyota Corolla is displayed.

For Pontiac Firebird, only the required columns are selected using:

**pontiac = cars.loc[cars["Model"] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]**

This displays the Model, mpg, hp, and wt of the Pontiac Firebird.

The `==` operator checks if the value in the Model column matches the given model name.

## Part C – Multi-Model Subsetting

Boolean indexing is used to select three car models:

* Datsun 710
* Lotus Europa
* Ferrari Dino

The rows are selected using their model names:

**selected_cars = cars.loc[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino')]**

The `|` symbol means **OR**, so a row is selected if its model matches any of the three names.

Only the following columns are kept:

**selected_cars = selected_cars[['Model', 'mpg', 'cyl', 'hp', 'gear']]**

The shape of the resulting DataFrame is checked using:

**selected_cars.shape**

The result is **(3, 5)**, which means there are **3 rows** and **5 columns**.
