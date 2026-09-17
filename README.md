# EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)
 Juliana Angelica L. Castro

2ECE-C

## Intended Learning Outcomes
At the end of this laboratory activity, the student should be able to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

# A. POSITIONAL AND LABEL-BASED SLICING
After loading cars, complete the following operations.

**a. Display the shape and complete list of column names of cars.**

CODE:
- cars.shape
- cars.columns

**b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.**

CODE:
- cars_6_to_10=cars.iloc[6:11]

  cars_6_to_10
  
**c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.**

CODE:
- cars_6_to_10.loc[0:0,['Model','mpg','cyl','hp','gear']]

**Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.**

# B. MODEL LOOKUP
Use Boolean indexing on the Model column to answer both requests.

**a. Display the complete row for Toyota Corolla.**

CODE:
- toyota=cars.loc[cars['Model']=='Toyota Corolla']

  toyota

**b. For Pontiac Firebird, display only Model, mpg, hp, and wt**

CODE:
- pontiacfirebird=cars.loc[cars['Model']=='Pontiac Firebird',['Model','mpg','hp','wt']]

  pontiacfirebird

**Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.**

# C. MULTI-MODEL SUBSETTING
**Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.**

**For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.**

CODE:
- selected_cars=cars[cars["Model"].isin(target_models)][["Model","mpg","cyl","hp","gear"]]

  selected_cars

**Required check: The final DataFrame must contain exactly three rows and five columns.**

CODE:
- selected_cars.shape
