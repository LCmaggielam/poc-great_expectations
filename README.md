# poc-great_expectations
Repo for sharing use-cases for great-expectations library with Databricks df

# Documentation and Extension
https://docs.greatexpectations.io/docs/reference/learn/data_quality_use_cases/integrity
Other extension
- gx.ExpectColumnKLDivergenceToBeLessThan
- gx.ExpectColumnValueZScoresToBeLessThan
- gx.ExpectColumnValuesToBeBetween (demo on this)

# Step 1 Install great_expectation library to your python

pip install great_expectations

# Step 2 Demo on gx.ExpectColumnValuesToBeBetween
- assume have a panda dataframe in databricks
- demo on one of the source load from informatica

# Explanation on the report:

- Success:
"success": true indicates that the expectation was met, meaning all checked values are within the specified range.

- Expectation Configuration:
    - Type:
        "type": "expect_column_values_to_be_between" specifies the type of expectation being evaluated.
    - Parameters:
        "column": "AWB_PRINT_COUNT" indicates which column was checked.
        "min_value": 1.0 and "max_value": 6.0 define the acceptable range for values in that column.

- Result:
    - Element Count:
        "element_count": 10000 shows the total number of elements (rows) checked.
    - Unexpected Count:
        "unexpected_count": 0 means there were no values outside the expected range.
    - Unexpected Percent:
        "unexpected_percent": 0.0 indicates that 0% of the values were unexpected.
    - Missing Count:
        "missing_count": 0 means there were no missing values in the checked column.
    - Missing Percent:
        "missing_percent": 0.0 indicates that 0% of the values were missing.

- Meta Information:
    The "meta" object is empty in this case, but it can hold additional metadata about the expectation.

- Exception Info:
    - Raised Exception:
        "raised_exception": false indicates that no exceptions were raised during the evaluation.
    - Exception Traceback:
        "exception_traceback": null means there was no traceback.
    - Exception Message:
        "exception_message": null confirms that no error message was generated.


# Use case
- could be use in data validation pipline or workflow to ensure data quality meets the defined expectations