Log of Data Fixes

This contains a record of the changes made to the data during the cleaning and merging process. Data cleaning and merging was done using Excel and PowerQuery on Excel.

1. The data was spread out over monthly spreadsheets which were consolidated using PowerQuery to combine all relevant data columns into one dataset for ease of analysis.
2. Extracted Year and Month data from gift_date column.
3. Converted gift_amount to number format instead of dollar formatting.
4. Donor names were anonymized and referenced using lookup tables (not available to maintain anonymity)
5. 36/1066 cells in the gift_constituency column were blank. At only 3.3% of the data and being unable to fill in the data, they were left blank.
6. Campaign_list column contained 11 blank cells and were left blank. 
7. A large portion of the fund_list column was cleaned using a lookup table to reference the proper labels. Where some rows contained extra lines, they were corrected by referring them to general operations (GENOP) or its corresponding name. 
  For example certain rows were recorded as "-----; GENOP" and was then adjusted to "GENOP".
8. The appeal_list column contained 27 blank rows and couldn't be filled in so they were left blank.
9. Extra columns like check_number or names associated with a donation in the dataset were removed due to its insignificance or sensitivity issues.
10. Duplicate columns for dates were created during the data merging step and was subsequently deleted after verifying that it contained the same information.
