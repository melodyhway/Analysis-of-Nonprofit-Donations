# Project Background

This project analyzes non-profit donations for an organization that serves the San Francisco Bay Area. The data contains records of donations made from June 2024 to June 2025 including data on donation dates, donation amounts, donor id, donor type, campaign id, fund allocation destination, records for recurring or annual donations. This project aims to use Excel, SQL, and Tableau to discover how donations are allocated, donation sources, investigating the effectiveness of different events in gathering donations. This project will also help identify the biggest donors in the system and identify seasonal patterns in donations to better understand donation patterns and increase future fundraising efforts during certain times like holidays or hosted events. 

Summary:
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


An Interactive Tableau Dashboard can be found [here](https://public.tableau.com/views/Analysisofnon-profitdonations/Non-ProfitDonationsDashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

Find the SQL queries to answer specific questions [here](https://github.com/melodyhway/Donations-Analysis-using-SQL/blob/8f98b82866f7878f72b89d0c21ab47cf334d4a83/SQLqueries.md)

# Overview of Findings 
This dataset on the donations made during June 2024 to June 2025 found that a total of $6,830,130.33 were donated to the organization. The top performing months occured during May 2025, June 2024, and December 2024. A large portion of the donations were made by Foundation donors indicating possible partnerships with these foundations that could further increase donation efforts. Some events hosted during certain times could also have an impact of the amount of donations. Notably, in May the Chef Gala was held increasing funding efforts. There was also End Of Year events that also have an impact on the donations made. Throughout this project, we will uncover inisghts about donor types, campaigns and events in order to gain a better understanding of the June 2024 - 2025 donation performance. 

\{Summary of Findings after being done\}

## Dashboard Overview 
<img width="1998" height="1598" alt="Non-Profit Donations Dashboard (2) (1)" src="https://github.com/user-attachments/assets/44db9f74-f07a-4c87-b183-9a0bd5e03717" />

### Overall Donation Trends

Taking a look at the overall donation trends, we see that June 2024, May 2025, and June 2025 performed exceptionally well compared to other months. Notably, the donor counts vary quite qidely across these top performing months. We see that May received 203 unqiue donations where June 2024, at similar donation totals, received only 46 unique donations. This may uncover an interesting discovery especially when we look at the hosted events during these times, analyze the distribution of donor types, or even the introduction of a new partnership. December also has a high volume of unique donations but didn't acheive similar amounts of total donations. 

<img width="1802" height="1590" alt="monthly donations" src="https://github.com/user-attachments/assets/1c51d89f-a1a8-4f63-b217-e5fdbe8805d1" />

<img width="2704" height="302" alt="monthly donations (2) (2)" src="https://github.com/user-attachments/assets/1e61dc91-a124-4985-9c0b-8c783f81f987" />

This graph shows the percentage change in donations per month where the red represents larger dips and greens represent larger percentage increases in donations. 

#### Impacts of certain events like Chef Gala, Holiday Gift Drive.

Donations peaked in May 2025 and when analyzing the donations made during May, it seems that a lot of the donations were made in support of the Chef Gala designed to support programs in supporting people entering the workforce by providing training and jobs to the non-profits participants. This graph shows how the chef gala accounted for $261,510 of donations made during May 2025. The rest are a variety of funding efforts from different organizations. 

<img width="2106" height="1590" alt="chef gala fundraising efforts" src="https://github.com/user-attachments/assets/8cf79012-1367-4aad-81cf-c7bec6c52625" />

In analyzing the proportion of donor types by month, this graph shows that a majority of donations are covered by Foundation donations. Out of the total sum of donations, 80.78% of the total donations were made by foundations, followed by 7.22% made by Individual donors. Foundations are likely the largest partners in the non-profit allowing for the organization to host potentailly host events in partnership with some of the foundations increasing donation efforts. Interestingly, because Individuals are the next highest percentage, it is important to acknowledge the strong impacts that individual donors make on the organization. 

<p align = "middle">
  <img width="450" height = "700" alt = "Monthly Donor Distribution" src="https://github.com/user-attachments/assets/875ba0bb-89f5-4c31-bf10-cb0a4ef64b0d" />
  <img width="450" height = "700" alt = "Total Donor Distribution" src="https://github.com/user-attachments/assets/9e481305-cc06-4749-b587-9d5ae949dbd5" />
</p>

#### Individual Donors








Stakeholder Questions: 
1. What were the total donations during the June 2024 - June 2025 time period?
2. What is the monthly total and monthly average of donations? Are there months that receive higher donations than others?
3. What is the seasonlity in donations? Do certain months perform better than others? 
4. Who are the top 5 largest donors? Who are the top 5 individual donors, foundation donors, and corporation donors.
5. What is the average donation size by gift constituency?
6. Where are the funds typically allocated towards? What is the percentage distribution? 
7. What percentage of donations came from the top 10 donors?
8. How diverse are the donations? Meaning what portion of donations were made by individuals, corporations, and foundations? Is there a need to diversify?
9. Which campaigns were more effective in getting donations?
