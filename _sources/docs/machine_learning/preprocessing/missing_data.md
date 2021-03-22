# Missing Data

## Identification of missing data

### Method 1

Missing data can be identified by 

```python
# To find the missing data in every column of pandas dataframe "df"
df.isna().sum()
```
  
### Method 2

Use **missingno** package.

To visualize the missing data
```python
import missingno as msno

# To visualiza the missing data in the dataframe "df"
msno.matrix(df)
```

## Handling missing data

There are no set of rules to drop columns with missing data. How much is too much is not defined. Columns having missing data should be analyzed for their relation with the target variable.

## References

- [How much missing data is too much? Multiple Imputation (MICE) & R](https://stats.stackexchange.com/questions/149140/how-much-missing-data-is-too-much-multiple-imputation-mice-r)
