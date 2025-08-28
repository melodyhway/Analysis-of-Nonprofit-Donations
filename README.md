# Project Background

This is a project analyzing non-profit donations for an organization that serves the San Francisco Bay Area. The data contains records of donations made from June 2024 to June 2025 including data on donation dates, donation amounts, donor id, donor type, campaign id, fund allocation destination, records for recurring or annual donations. This project aims to use Excel, SQL, and Tableau to discover how donations are allocated, donation sources, investigating the effectiveness of different events in gathering donations. This project will also help identify the biggest donors in the system and identify seasonal patterns in donations to better understand donation patterns and increase future fundraising efforts during certain times like holidays or hosted events. 

Summary of Project:
## Insights and Recommendations 


## Data Structure and Data Validation
The donations contains 1066 records on the donations made during the June 2024 - 2025 fiscal year. It contains the following columns. 

| Column Name | Data Type | Descriptor |
| :------- | :------: | :-------|
| Gift_Date  | Date  | Donation Date |
| Gift_Amount| float  | Donation Amount (USD)|
| Donor_id | string  | Donor (anonymized) |
| Gift_Constituency | string  | Donor Type (individual, foundation, corporation etc) |
| Campaign_id| string  | AN24/AN25 |
| Fund List| string  | Donation Allocation data |
| Appeal List| string  | Information on recurring or annual donations |

### Caveats with the data
While the data contains a rich variety of information, there were several instances of data logging errors including misaligned dates, total donation calculations, duplicate columns, errors, and blank values. These issues were addressed using data cleaning methods through Excel. 

A log of fixes can be found [here](https://github.com/melodyhway/Donations-Analysis-using-SQL/blob/ec97ac7fdaa82c0d7fb66a9f593de10ed51d0878/datafixes.md)


Interactive Dashboard

SQL queries to answer specific questions 
