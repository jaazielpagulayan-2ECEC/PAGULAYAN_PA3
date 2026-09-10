# Jaaziel Raighne M. Pagulayan
## 2ECE-C
## 09/10/2026

### I. Intended Learning Outcomes 

At the end of this laboratory activity, the student should be able to:
1. Load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. Extract a well-defined subset of data without changing the source data.

### A. POSITIONAL AND LABEL-BASED SLICING

After loading cars, complete the following operations.

a. Display the shape and complete list of column names of cars.

b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.

c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.ion

`Explanation`:

* 'import pandas as pd' loads the pandas Library into Python and gives it the shortcut name pd, so it's easier to type. Pandas is used to handle tabular data (like spreadsheets).


* 'cars = pd.read_csv('cars.csv')' reads the dataset file named 'cars.csv' using pandas and saves the table into a variable called cars.

* 'cars.shape' Returns the dimensions of the table as (rows, columns).

* 'cars.columns' displays the names of all the columns in the dataset

* 'cars_6_to_10 = cars.iloc[[0, 5,6,7,8,9]]' uses .iloc to pick specific rows by their index numbers: rows 0, 5, 6, 7, 8, and 9. It saves this small chunk of data into a new variable called cars_6_to_10

* 'cars_6_to_10.loc[[0,5,6,7,8,9],['Model','mpg','cyl','hp','gear']]' uses .loc to select specific rows (0, 5, 6, 7, 8, 9) AND specific column names ('Model', 'mpg', 'cyl', 'hp', 'gear'). This filters down the table so only those specific cells show up.

```python
import pandas as pd

cars = pd.read_csv('cars.csv')
cars

cars.shape

cars.columns

cars_6_to_10 = cars.iloc[[0, 5,6,7,8,9]]
cars_6_to_10

cars_6_to_10.loc[[0,5,6,7,8,9],['Model','mpg','cyl','hp','gear']]
```

### B. MODEL LOOKUP

Use Boolean indexing on the Model column to answer both requests.

a. Display the complete row for Toyota Corolla.

b. For Pontiac Firebird, display only Model, mpg, hp, and wt.

Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

`Explanation:`

* 'toyota = cars.loc[cars['Model'] == 'Toyota Corolla']' searches the 'Model' column for the exact string 'Toyota Corolla'. It filters out everything else and stores that single row in the variable toyota.

* 'pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model','mpg','hp','wt']]' finds the row where 'Model' is 'Pontiac Firebird', but only extracts four specific columns: 'Model', 'mpg', 'hp', and 'wt'. Saves this filtered result into pontiac.

```python
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
toyota

pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model','mpg','hp','wt']]
pontiac
```


###Required check: 
The final DataFrame must contain exactly three rows and five columns.

 `Explanation:` 
 
 * 'selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model','mpg','cyl','hp','gear']]' This uses pandas .loc[] to filter specific rows and columns simultaneously, while this operator '|' selects any row where the model name matches 'Datsun 710', 'Lotus Europa', or 'Ferrari Dino' then ['Model','mpg','cyl','hp','gear'] specifies the exact list of columns to return for those matching rows.

 * 'selected_cars.shape'  returns the dimensions of the table as (rows, columns). 

   
```python

selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model','mpg','cyl','hp','gear']]
selected_cars

selected_cars.shape

```
