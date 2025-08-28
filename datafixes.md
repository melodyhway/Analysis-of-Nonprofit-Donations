Log of Data Fixes

This contains a record of the changes made to the data during the cleaning and merging process. Data cleaning and merging was done using Excel and PowerQuery on Excel.

1. Extracted Year and Month data from gift_date columns.
2. Converted gift_amount to number format instead of dollar formatting.
3. Donor names were anonymized and referenced using lookup tables.
4. 36/1066 rows in the gift_constituency column were blank. At only 3.3% of the data and being unable to fill in the data, they were left blank.
5. Campaign_list column contained 11 blank rows. 
6. A large portion of the fund_list column was cleaned using a lookup table to reference the proper columns. Where some rows contained extra lines, they could be fixed by referring them to general operations (GENOP) or its corresponding name. 
  For example some rows were recorded as "-----; GENOP" and was then adjusted to "GENOP".
7. The appeal_list column contained 27 blank rows and couldn't be filled in. 
8. Extra columns in the dataset were removed due to its insignificance or sensitivity.
