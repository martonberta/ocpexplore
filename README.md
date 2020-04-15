# ocpexplore
Simple functions for tabular data exploration

## Dependencies
The following packages are required:
* pandas
* numpy
* matplotlib.pyplot
* seaborn
* warnings

## Installation
Please run the following code to install the package
``` js
pip install ocpexplore
```
Please use the following code to import the functions. (The recommended shortcut for using the package is 'expl')
``` js
import ocpexplore.ocpexplore as expl
```
## Functions
### value_counter(df, obj_cols_only = True, unique_limit = 25)
__Purpose__\
Apply the value counts method to specific columns of a dataframe

__Arguments__
* df: Pandas dataframe
* obj_cols_only: apply function to columns with object dtype only
* unique_limit: apply function to columns which have less unique observations than the provided limit

__Output__\
For every relevant column the function prints counts and ratios of unique values and also a barchart with for better visibility.

__Example__
``` js
value_counter(df)
```
&nbsp;

### check_ID(df)
__Purpose__\
Check how many unique values are present in each column of the provided dataframe

__Arguments__
* df: Pandas dataframe

__Output__\
Prints the number of unique values in each column, and the ratio of the unique values to all values

__Example__
``` js
check_ID(df)

# or

check_ID(df[['relevant_col1', 'relevant_col2']])
```
&nbsp;

### check_NA(df)
__Purpose__\
Check how many missing values are present in each column 

__Arguments__
* df: Pandas dataframe

__Output__\
Prints the number and ratio of missing values in each column and also a barchart for better visibility.

__Example__
``` js
check_NA(df)
```
&nbsp;

### plot_continuous(df)
__Purpose__\
Visually examine the distribution of values in each numerical column in a dataframe.

__Arguments__
* df: Pandas dataframe with numerical columns only.

__Output__\
Creates a boxplot and a density plot for each column in the provided dataframe. 

__Example__
``` js
plot_continuous(df)

# or

plot_continuous(df[['numerical_col1', 'numerical_col2']])
```
&nbsp;

### describe_continuous(df, interpolation = 'nearest')
__Purpose__\
Examine the distribution of values in each numerical column in a dataframe with simple descriptive statistics.

__Arguments__
* df: Pandas dataframe with numerical columns only.
* interpolation: interpolation method used for quantile calculation. For more info, please see pandas.DataFrame.quantile

__Output__\
Creates a dataframe which contains the descriptives for the columns in the input dataframe.

__Example__
``` js
describe_continuous(df)

# or

describe_continuous(df[['numerical_col1', 'numerical_col2']])
```
&nbsp;

### tail_density_table(df, interpolation = 'nearest')
__Purpose__\
Examine the number of outliers and extreme values for each row in a dataframe.

__Arguments__
* df: Pandas dataframe with numerical columns only.
* interpolation: interpolation method used for quantile calculation. For more info, please see pandas.DataFrame.quantile

__Output__\
Creates a dataframe which contains the number of outliers and extreme values for the columns in the input dataframe.

__Example__
``` js
tail_density_table(df)

# or

tail_density_table(df[['numerical_col1', 'numerical_col2']])
```
&nbsp;

### obs_by_date(column, date_aggregation = 'M')
__Purpose__\
Aggregates the number of observations in a date column for a given period of time.

__Arguments__
* column: Pandas series in datetime format.
* date_aggregation: Level of aggregation. Can be
  - days: 'D'
  - months: 'M'
  - years: 'Y'

__Output__\
Returns the results of a value_counts method which was applied to the aggregated date series and also creates a barplot for better visibility.

__Example__
``` js
obs_by_date(series)
```
&nbsp;

### values_by_date(df, date_column, date_aggregation = 'M')
__Purpose__\
Observe the distribution of values over time.

__Arguments__
* df: Pandas dataframe with one date column and numerical columns
* date_column: name of the data column in the input dataframe.
* date_aggregation: Level of aggregation. Can be
  - days: 'D'
  - months: 'M'
  - years: 'Y'

__Output__\
Returns boxplots with x axis as aggregated date and y as value for every numerical variable in the input database.

__Example__
``` js
values_by_date(df,'date_col')
```
