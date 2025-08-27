# Donations-Analysis-using-SQL
This is part of a portfolio project investigating the donations made to a non profit organization. 

## Introduction
This dataset contains 1106 records of donations made towards a non-profit serving the San Francisco Community spanning from June 2024 to June 2025. The dataset contains donation dates, donation amounts, donor id, donor type, campaign id, fund allocation destination, records for recurring or annual donations. This project aims to use SQL to discover how donations are allocated, the source of donations analyzing the campaign year's effectiveness in gathering donations, analyzing the best times for donations, comparing donation amounts made by individuals vs corporations vs foundations to further discover how to effectively campaign for donors. This project will also help identify the biggest donors in the system and identify seasonal patterns in donations to better understand donation patterns and increase efforts in fundraising during certain times like holidays or events. 

### Caveats with the data
While the data contains a rich variety of information, there were several instances of data logging errors including misaligned dates, total donation calculations, duplicate columns, errors in records, and blank values, these issues were addressed using data cleaning methods through Excel. For example, date errors were cross-validated using the original dataset to reference the proper dates, duplicate columns were deleted, errors in records were addressed using a XLOOKUP function to reassign proper values. Blank values were left blank in instances where that data could not be filled in. Overall blank rows only affected a small portion of each column so most were left as is. 

### Table Structure

| Column Name | Data Type |
| :------- | ------: |
| Gift_Date  | Date  |
| Gift_Amount| float  | 
| Donor_id | VARCHAR  |
| Gift_Constituency | VARCHAR  |
| Campaign_id| VARCHAR  |
| Fund List| VARCHAR  |
| Appeal List| VARCHAR  |


### Stakeholder Questions
1. What were the total donations during the June 2024 - June 2025 time period?
2. What is the monthly total and monthly average of donations? Are there months that receive higher donations than others?
3. What is the seasonlity in donations? Do certain months perform better than others? 
4. Who are the top 5 largest donors? Who are the top 5 individual donors, foundation donors, and corporation donors.
5. What is the average donation size by gift constituency?
6. Where are the funds typically allocated towards? What is the percentage distribution? 
7. What percentage of donations came from the top 10 donors?
8. How diverse are the donations? Meaning what portion of donations were made by individuals, corporations, and foundations? Is there a need to diversify?
9. Which campaigns were more effective in getting donations?

# Table Example
```
SELECT * FROM donations LIMIT 7;
```
<img width="1037" height="252" alt="Screenshot 2025-08-26 at 5 43 50 PM" src="https://github.com/user-attachments/assets/523014cc-47f0-4a7b-b2b8-d1cd934e8fc6" />



### 1. Total Donations 
```
SELECT sum(gift_amount) as TOTAL_DONATIONS FROM donations;
```
<img width="164" height="64" alt="Screenshot 2025-08-26 at 5 28 55 PM" src="https://github.com/user-attachments/assets/be93bc90-a45c-4d30-be1c-3973800852b2" />

The amount of donations totaled $6,921,752 for a period of 1 year from June 2024 to June 2025. 

### 2. What is the monthly total and monthly average of donations?
```
SELECT Year, Month, 
sum(gift_amount) AS donation_total, 
avg(gift_amount) AS avg_donations 
FROM donations
GROUP BY Year, Month
ORDER BY Year, Month;
```

<img width="949" height="421" alt="Screenshot 2025-08-26 at 5 52 34 PM" src="https://github.com/user-attachments/assets/efaf4428-aa3d-445c-9eaf-84246b433e5e" />

Organized by year and month, sum of donations range from $38,549.01 to $1,371,161.52. The least amount of total donations occured in January 2025 and the highest amount of total donations occured in May 2025. Average monthly donations ranged from $700.89 to $28,239.77.

### 3. 
